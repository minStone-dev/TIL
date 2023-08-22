# Glide란?
안드로이드 라이브러리중 하나로 url을 이미지로 변환시켜주는 라이브러리이다.<br>
Glide는 이미지 로딩 프레임워크이다. Glide는 이미지, 영상 썸네일, GIFs를 가지오거나, 디코딩, 보여줄 수 있다. <br>
빠르고 유능하다는 점 덕분에 많은 개발자들에게 인기 있는 이미지 로딩 프레임워크이다.

## Glide 사용법
- Glide를 사용하기 위해서 Dependency 추가하기 
  ```kotlin
  implementation 'com.github.bumptech.glide:glide:4.12.0'
  annotationProcessor 'com.github.bumptech.glide:compiler:4.12.0'
  ```
### 이미지 로드하기 
<br>기본 사용법은 매우 간단하다 **with()** 메서드는 **Context, Activity, Fragment, View**를 파라미터로 받고<br>
  **load()** 메서드는 **Bitmap, Drawable, String, Uri, File** 등의 이미지 정보를 가지고 있는 객체를 파라미터로 받고<br>
  마지막 **into()** 메서드는 이미지를 넣을 **ImageView**를 파라미터로 받아준다.
 ```kotlin
Glide.with(context)
  .load(이미지 경로)  // ex) R.drawable.img
  .into(imageView) // ex) findViewById(R.id.img_view),binding.imgView
   ```

### 추가적인 메서드
- override()
  이미지 사이즈를 조절하는 메서드
  ```kotlin
  Glide.with(context)
  .load(이미지 경로)
  .override(Int,Int) // 순서대로 넓이(width),높이(height)
  .into(imageView)
   ```

- placeholder()
  로딩 중일때 보일 이미지를 보여준다
  ```kotlin
  Glide.with(context)
  .load(이미지 경로)
  .placeholder(이미지 경로) // ex) R.drawable.img
  .into(imageView)
   ```
  
- error()
  이미지 로딩 실패 시 보여줄 이미지를 보여준다.
  ```kotlin
  Glide.with(context)
  .load(이미지 경로)
  .error(이미지 경로) // ex) R.drawable.img
  .into(imageView)
   ```
  
- asGif()
  gif 이미지를 보여준다.
  ```kotlin
  Glide.with(context)
  .asGif
  .load(이미지 경로)
  .into(imageView)
   ```
  
- thumbnail()
  로딩되는 이미지를 섬네일 이미지로 사용한다
  ```kotlin
  Glide.with(context)
  .load(이미지 경로)
  .thumbnail(0~1f) // ex) 0.1f == 10%,0.5f == 50%
  .into(imageView)
   ```

# Fresco란?
facebook에서 출시한 이미지 로딩 라이브러리로 속도가 매우빠르다 <br>
앞서 소개한 Glide,Picasso 보다 이미지 로딩 속도가 빠르다. (coil과 유사한것 같다)<br>
- ImageView가 아닌 DraweeView를 사용한다.
- DraweeView가 wrap_content를 지원하지 않아 요청할 이미지의 정확한 사이즈를 지정해야 한다.
- SimpleDraweeView는 ImageView를 부모 클래스로 가지고 있다 하지만, 절대로 setImageDrawable 같은 직접적으로 접근하는 것을 사용하지 않아야 한다.

## Fresco사용법

- Fresco를 사용하기 위해 Dependency 추가하기
  ```kotlin
  implementation 'com.facebook.fresco:fresco:2.5.0'
    
  //앱의 필요에 따라 선택적 모듈 추가
  implementation 'com.facebook.fresco:imagepipeline-okhttp3:2.1.0'
  implementation 'com.facebook.fresco:animated-base:2.5.0'
    
  // 애니메이션 GIF 지원용
  implementation 'com.facebook.fresco:animated-gif:2.6.0'
 
  // 애니메이션 WebP 지원용
  implementation 'com.facebook.fresco:animated-webp:2.6.0'
  implementation 'com.facebook.fresco:webpsupport:2.6.0'
    
  // Android 지원 라이브러리 제공(이미 이와 유사한 종속성이 있을 수 있음)
  implementation 'com.android.support:support-core-utils:24.2.1'
  ```
- xml 파일에 DraweeView 추가하기
  ```kotlin
  <com.facebook.drawee.view.SimpleDraweeView
    android:id="@+id/imageView"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    />
  ```
- 사용할 Activity에서 Fresco 초기화 하기
  ```kotlin
  Fresco.initialize(this)
  ```
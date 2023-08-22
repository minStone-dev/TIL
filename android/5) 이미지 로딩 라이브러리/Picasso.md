# Picasso란?
Square에서 만든 Picasso는 최소한의 메모리로 이미지의 다양한 Transformation을 지원하며, <br>
자동으로 메모리 & 디스크 캐싱, 어댑터에서 ImageView를 재활용 및 다운로드 취소가 가능하다는 점을 강조하고 있다.

- 속도 : Glide에 비해 느리다
- Glide에 비해 화질이 좋다
- 메모리를 적게 차지한다(가볍다)
- but 큰 이미지를 사용할경우 glide에 비해 메모리를 많이 차지한다
- 원본 이미지 크기를 그대로 비트맵에 그린 후에 이미지뷰에 적용한다.
- 고화질의 이미지를 로드한다면 OOM(Out Of Memory)을 발생시킬 수 있다.
- Gif 미지원

## Picasso 사용법
사용법은 Glide와 비슷하다.

- Picasso를 사용하기 위해 Dependency 추가하기
  ```kotlin
  implementation 'com.squareup.picasso:picasso:2.71828'
  ```
- load()
  ```kotlin
  Picasso.get()
    .load(Url) //ex)"https://minStone.com/image.jpg"
    .into(ImageView) 
  ```
- resize(Int, Int)
  ```kotlin
  Picasso.get()
    .load(Url) //ex)"https://minStone.com/image.jpg"
    .resize(200, 200) // 이미지 크기를 200X200으로 조정
    .into(ImageView) 
  ```
  
- fit()
  ```kotlin
  Picasso.get()
    .load(Url) //ex)"https://minStone.com/image.jpg"
    .fit() // imageView의 크기에 맞춰 이미지 크기 조절
    .into(ImageView) 
  ```
- error()
  ```kotlin
  Picasso.get()
    .load(Url) //ex)"https://minStone.com/image.jpg"
    .error(R.drawable.error) // 로딩 실패 시 에러 이미지를 표시
    .into(ImageView) 
  ```
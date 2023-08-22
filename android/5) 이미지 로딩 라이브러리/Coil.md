# Coil 이란?
Coil은 **Co**routine **I**mage **L**oader의 약자이며 **Kotlin Coroutines(코루틴)** 으로 만들어진 <br>
가벼운 Android 백앤드 **이미지 로딩 라이브러리**입니다.

## Coil의 장점
- 빠르다
  - Glide,Fresco보다 상대적으로 가볍다.<br>
        메모리와 디스크의 캐싱,메모리의 이미지 다운 샘플링,Bitmap 재사용,<br>
        일시정지/취소의 자동화 등등 수많은 최적화 작업을 수행하므로 처리속도가 매우 빠르다.
- 가볍다 
  - Coil은 최대 2000개의 method들을 APK에 추가합니다(이미 OkHttp와 Coroutines을 사용중인 앱에 한하여),<br>
        이는 Picasso 비슷한 수준이며 Glide와 Fresco보다는 적습니다.
- 사용성이 좋다
  - 코루틴이 기본이지만 메인까지는 아니며 심플함과 최소한의 보일러 플레이트(boilerplate)를 위하여 <br>
    Kotlin의 기능을 활용하여 Kotlin을 잘 다룬다면 사용하기가 매우 쉽다.
  - Coil의 이미지 파이프라인(PipeLine)은 크게 세 가지로 구성됩니다. Mappers, Fetchers, Decoders<br>
    이러한 인터페이스를 사용하여 기본 이미지 로딩 기능을 강화하거나 재정의하고 <br>
    Coil에 새로운 파일 형식에 대한 지원을 추가할 수 있습니다.
  - Kotlin으로 개발 되었으며 Coroutines, OkHttp, Okio, AndroidX Lifecycles등의 최신 라이브러리를 사용합니다.
## Coil의 단점
- Android SDK 버전 14 부터 지원을 하지만 신뢰성이 낮아 실무에서 사용하는 기업이 적다.
- Kotlin,Coroutines에 대해 잘 모른다면 사용이 어려울수도 있다.

## Coil 사용법

- Coil을 사용하기 위해 Dependency 추가하기
  ```kotlin
  implementation("io.coil-kt:coil:0.10.0")
  ```
  
- load 메서드 사용
  ```kotlin
  imageView.load("https://minStone.android/image.jpg") // URL
  imageView.load(R.drawable.image) // Resource
  imageView.load(File("/path/to/image.jpg")) // File
  ```
  
- 이미지를 후처리 하거나 placeholder 를 적용하려면 아래처럼 적용하면 된다.
  ```kotlin
  imageView.load("https://www.example.com/image.jpg") {
  crossfade(true)
  placeholder(R.drawable.image)
  transformations(CircleCropTransformation()) // 이미지를 원형으로 자른다
  }
  ```
  위의 예제에서 사용한 CircleCropTransformation() 이외에도 다른 Image Transformations들을 제공한다.
  -  BlurTransformation :
    이미지를 흐릿하게 보이기하는 가우시안 블러(Gaussian Blur)를 적용합니다.
  -  CircleCropTransformation :
    이미지의 중심을 기준으로 원형으로 이미지를 자릅니다. (예. 카카톡의 원형 프로필 이미지)
  -  GrayscaleTransformation :
    그레이스케일로 음영처리를 적용합니다.
  -  RoundedCornersTransformation :
    사이즈에 맞도록 이미지를 자르고 이미지 모서리를 둥글게 라운드를 적용합니다.
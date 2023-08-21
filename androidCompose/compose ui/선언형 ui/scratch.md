# 선언형 UI란?
어떻게 무엇을 할지 대신 **무엇을(How) 해야하는지** 기술하는 방법 이다.<br>
**UI = s(state)** 이라고 표현할수 있다.

## 명령형 UI vs 선언형 UI

### 명령형 UI
안드로이드 에서 기존에 UI를 그리던 방식으 아래와 같은 특징을 가진다
- UI를 업데이트 하기위해 view객체를 가져와야 한다
  - findViewById()와 같은 함수가 있다.
- 뷰는 상태를 가지고 있어 함수로 상태를 가져옴
  - getText() 같은 함수로 가져올수 있다
- View의 상태를 업데이트 하기 위해 여러 함수를 사용한다.
  - setText() 로 Text 업데이트
  - container.addView() 로 container 업데이트
  - img.setImageBitmap() 로 img 업데이트
  
- 위의 방법들을 viewBinding or DataBinding을 사용해 조금더 간결하게 처리가 가능하다.

### 선언형 UI


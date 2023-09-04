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
선언형 UI에서는 XML 을 사용하지 않고, 코드로 UI를 작성한다.<br>
androi Jetpack Compose는 @Composable 함수로 이루어져 있다.<br>
```kotlin
//ex
@Composable
fun OnboardingScreen(onContinueClicked: () -> Unit) {
    Surface {
        Column(
            modifier = Modifier.fillMaxSize(),
            verticalArrangement = Arrangement.Center,
            horizontalAlignment = Alignment.CenterHorizontally
        ) {
            Text("Welcome to the Basics CodeLab!")
            Button(
                modifier = Modifier.padding(vertical = 24.dp),
                onClick = onContinueClicked
            ) {
                Text("Continue")
            }
        }
    }
}
```
선언형 ui의 장점
- 직관적이다. 하나의 포인트에서 화면 구성, 이벤트 내용, 애니메이션 등 UI의 모든 것을 알 수 있다.
- 재사용성이 좋다. 기본 호출만으로 UI를 재사용할 수 있다. UI를 수정할 때 하나의 영역만 확인 후 수정하면 되니 작업 효율성도 올라가게 된다.
- 방향 흐름으로 인한 SideEffect 제거할 수 있다. 단방향 흐름의 성향이 강한 선언형 UI의 특징에 따라 호출된 영역과 호출한 영역의 구분이 확실하게 독립적이다. 따라서 SIdeEffect 차단에 도움이 된다.

단점
- 방대한 코드가 단점. 한 곳에서 UI의 모든 것을 정의하기 때문에 코드가 방대해진다.
- 재사용성의 어두운면이 존재한다. 개발자의 활용 부족으로 마구잡이로 개발하면 중복 코드가 많아져 유지보수가 힘들어진다.
- 선언형은 결국 명령형의 추상화이다. 가독성은 좋지만 과정이 없기에 불호하는 사람이 있기 마련이다.

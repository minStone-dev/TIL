# 형변환

형변환 이란 **값을 다른 타입으로 변환**하는것 이다.<br>
형변환은 암시적 형변환과 명시적 형변환으로 나뉘는데<br>
코틀린은 암시적 형변환을 지원하지 않는다.

## 암시적 형변환(자동 타입 변환)
암시적 형변환이란 **컴파일러가 자동**으로 수행하는 형변환을 말하며<br>
개발자가 강제로 타입변환을 하지 않는경우를 말한다
```kotlin
var a: Int = 1// Int형으로 선언
var b: Double = a (X) // 타입 불일치 에러
var c: Int = 123.1 // 타입 불일치 에러
```
## 명시적 형변환(강제 타입 변환)
개발자가 강제적으로 타입을 변환하는 경우를 말한다.
```kotlin
var a: Int = 1 // Int형으로 선언
var b: Double = a.toDouble() // 명시적 형변환
println(b) // 1.0출력
```

### 명시적 형변환 매서드
- toByte() : Byte로 변환
- toShort() : Short로 변환
- toInt() : Int로 변환
- toLong() : Long으로 변환
- toFloat() : Float으로 변환
- toDouble() : Double로 변환
- toChar() : Char로 변환
- toString() : String으로 변환
```kotlin
var a: Int = 97 // Int형으로 선언
var b: Char = a.toChar() // Char 형변환
println(b) // a 출력(아스키코드 97 == a)

var c: Int = 2_147_483_647 // int선언
var d: Short = c.toShort() // Short 형변환
println(d) // -1 출력(Short형의 최댓값을 벗어났기 때문)
```

## is 와 as
### is
- 자료형을 검사하기 위한 키워드 이다.
- Java의 instanceof()와 비슷한 역할을 한다.
- Any 타입에 대한 자료형을 검사한다. 정확히는 객체가 어떤 유형인지 확인하는데에 사용된다.
- 추후에 보완 예정

```kotlin
var a: Any = 1 // Any 타입으로 선언해야 한다
var b: Any = 'a'
if(a is Int) println(a) // a가 Int형 이라면 a값 출력
if(b !is String) println(b) // b가 Int형이 아니라면 b값 출력
```
### as

- 형변환을 하는데에 사용된다.
- 정확히는 객체의 타입을 변환하는데 사용이된다
- 추후에 보완 예정

```kotlin
val a: Any = 1
val b: String? = a as? String // String이 아니면 예외(에러)대신 null값을 반환

val c: Any = 1
val d: String = c as String // String이 아니므로 error 발생
```
# 자료형
변수라는 메모리 공간에 저장되는 정수,실수,문자 등등 과 같은 **데이터형식(Type)** 을 자료형 이라고 한다.<br>
코틀린 에서의 자료형의 종류는 아래와 같은 것들이 있다.
## 정수형
- Byte : 1byte(8bit)
- Short : 2byte(16bit)
- Int : 4byte(32bit)
- Long : 8byte(64bit)

```kotlin
var a: Byte = 1 //Byte형으로 선언
var b: Short = -1 //Short형으로 선언
var c: Int = 123_456_789 // _(언더바)을 통해 자릿수를 구분할시 코드 가독성이 좋아짐
var d: Long = 2_147_483_648 //Long 형으로 선언
```

### 코틀린의 자료형 추론
코틀린에서는 자료형추론을 통해 자료형을 지정하지않고 변수를 선언해도 <br>
자동으로 **변수의 자료형을 추론해서 나타낸다.**

```kotlin
var a = 123 // Kotlin은 기본적으로 Int범위내에 있는 정수는 Int형으로 추론
var b = 123L // 정수뒤에 L을 붙이면 Long형으로 추론
var c = 2147483648 // Int최댓값을 벗어났기 때문에 Long형으로 추론
```

## 부호없는 정수 자료형(unsigned)
- UByte : 1byte(8bit)
- UShort : 2byte(16bit)
- UInt : 4byte(32bit)
- ULong : 8byte(64bit)

```kotlin
var a: UByte = 128u // UByte형으로 선언
var b: UShort = -1u(X) // unsigned 즉,부호가 없기 때문에 음수 저장 불가능
var c: UInt = 2147483648u // 음의 정수가 없기 때문에 일반적인 Int형 보다 더 많은 값 저장 가능
var d: ULong = 20060818u // 반드시 자료형을 넣어주고 뒤에 u라고 명시해 줘야함
```
## 실수형
- Float : 4byte(32bit)
- Double : 8byte(64bit)

```kotlin
var a: Double = 128.5 // Double형으로 선언
var b = 123.5 // kotlin은 기본적으로 실수를 Double형으로 추론
var c: Float = 123.5 // Float형으로 선언
var d = 123.5f // 실수뒤에 f를 붙이면 Float으로 추론
var e: double = 123.4e-2 // 부동소수점 방식으로 소수점을 이동한다 e,E로 표현한다,왼쪽으로 2칸이동
var f: ULong = 12.345E2 // 오른쪽으로 소수점 2칸 이동 
```
## 문자
- Char : 2byte(32bit) // 'a' 'b' 'c' 등 한 글자

```kotlin
var a = 'A'// Char형으로 추론
var b = "abc"(X) // 문자 하나만 지정가능
var c: Char //변수를 선언만 할 경우 자료형을 명시해줘야 함
```
## 문자열
- String : 가변적

```kotlin
var a: String = 'A'(X)// ''가 아닌 ""를 사용해야함
var b = "abc"(X) // String형으로 추론
```

## 논리형
- Boolean : 1bit // true,false

```kotlin
var a = true// Boolean형으로 추론
var c: Boolean //변수를 선언만 할 경우 자료형을 명시해줘야 함
```
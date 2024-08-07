# 1. 자바(JAVA) 란 ?

썬 마이크로시스템즈에서 개발하여 발표한 객체지향 프로그래밍 언어이다. 풍부한 클래스 라이브러리(Java API)를 통해 필요한 요소들을 기본적으로 제공하기 때문에 잘 활용한다면 강력한 기능의 자바 프로그램을 작성할 수 있다.

<br>

## 자바언어의 특징

- 운영체제에 독립적이다
- 객체지향언어
- 비교적 배우기 쉽다.
- 자동 메모리 관리(Garbage Collection)
- 네트워크와 분산처리를 지원
- 멀티쓰레드를 지원
- 동적 로딩(Dynamic Loading) 지원

<br>



## 프로그램 작성하기

자바에서 모든 코드는 반드시 클래스 안에 존재해야 하며, 서로 관련된 코드들을 그룹으로 나누어 별도의 클래스를 구성하게 된다. 그리고 이클래스들이 모여 하나의 Java 애플리케이션을 이룬다.

```java
class 클래스이름 {
  public static void main(String[] args) // main메서드의 선언부 
  {
    // 실행될 문장
  }
}
```

모든 클래스가 main 메서드를 가지고 있어야 하는 것은 아니지만, 하나의 Java 애플리케이션에는 main메서드를 포함한 클래스가 반드시 하나는 있어야 한다. main 메서드 없이는 Java 애플리케이션은 실행될 수 없다.

<br>

## 주석

주석을 이용하여 코드에 대한 설명이나 작성사, 작성일시, 변경이력 등의 정보를 제공해주어 프로그램을 이해하거나 협업 시 도움이 될 수 있다.

> **범위 주석** : /* 와 */ 사이의 내용을 주석으로 간주함.
> **한줄 주석**: // 부터 라인 끝까지의 내용을 주석으로 간주함.

```java
/*
Date : 2024. 6. 24
Author : 민기
*/

class Hello {
  public static void main(String[] args)  /* 프로그램 시작*/ 
  {
    System.ut.println("Hello World!!"); // Hello World!! 출력
  }
}
```

-------------

<br>



# 2. 변수

변수란, 단 하나의 값을 저장할 수 있는 메모리 공간이다. 하나의 변수에는 하나의 값만 저장할 수 있어서, 새로운 값을 저장하면 기존의 값은 사라진다.

<br>

## 변수의 선언

```java
int age; // 타입은 int(정수형), 이름은 age의 변수를 선언
```

변수타입은 변수에 저장될 값이 정수형, 실수형, 문자형 등의 타입을 지정하는 것이다.

변수이름은 변수에 이름을 붙여주어 값을 저장하고 읽어올 수 있다. 같은 이름의 변수가 여러 개 존재해서는 안된다.



<br>

## 변수의 초기화

변수의 초기화란, 변수를 사용하기 전에 처음으로 값을 저장하는 것을 의미한다.

변수를 선언한 이후 변수를 사용할 수 있으나, 그 전에 변수를 '초기화'해야 한다. 전에 다른 프로그램에 의해 저장된 쓰레기값이 남아있을 수 있기 때문이다.

```java
int age = 20; // 정수형 변수 age를 선언하고 20으로 초기화

int a, b;  // 여러 변수를 한 줄에 선언이 가능하다.
int x = 0, y = 0; 
```

<br>

## 변수의 명명규칙

프로그래밍에서 사용하는 모든 이름을 '식별자(identifier)' 라고 하는데, 식별자는 같은 영역 내에서 서로 구분(식별)될 수 있어야한다. 그리고 식별자를 만들 때는 다음과 같은 규칙을 지켜야 한다.

> **1. 대소문자가 구분되며 길이에 제한이 없다.**
>
> **2. 예약어(keyword)를 사용해서는 안 된다.**
>
> **3. 숫자로 시작해서는 안 된다.**
>
> **4. 특수문자는 '_'와 '$'만을 허용한다.**

<br>

## 권장하는 규칙들

> **1. 클래스 이름의 첫 글자는 항상 대문자로 한다.**
>
> **2. 여러 단어로 이루어진 이름은 단어의 첫 글자를 대문자로 한다.**
>
> **3. 상수의 이름은 모두 대문자로 한다. 여러 단어로 이루어진 경우 '_'로 구분한다**

<br>



##  변수의 타입

<img width="488" alt="image" src="https://github.com/user-attachments/assets/ba953389-fa09-43f7-9074-4adf873f1169">



이러한 값의 종류에 따라 값이 저장될 공간의 크기와 저장형식을 정의한 것이 자료형(data type)이다. 자료형은 기본형과 참조형으로 나뉜다.

>**기본형 (primitive type)** - 실제 값(data)를 저장
>
>  - 논리형(boolean), 문자형(char), 정수형(byte, short, int, long), 실수형(float, double)
>
>**참조형(reference type)**
>
>- 객체의 주소를 저장한다.

<br>

## 참조변수 선언 방법

```java
클래스이름 변수이름;

Date today = new Date(); // Date객체를 생성하여, 그 주소를 today에 저장
```



<br>

## 기본형의 종류와 크기

![capture 119](https://github.com/user-attachments/assets/8ea2e476-c961-48d9-9a47-6e261af5ce40)



<br>

## 상수

상수(constant)는 값을 저장할 수 있는 공간이지만, 한 번 값을 저장하면 다른 값으로 변경할 수 없다. 상수를 선언하는 방법은 변수와 동일하나, 변수의 타입 앞에 'final'을 붙여주면 된다. 상수는 반드시 선언과 동시에 초기화해야 한다.

```java
final int MAX_NUMBER = 10; // 여러 단어로 이루어져있는 경우 '_'로 구분
```

<br>

## 리터럴(literal)

리터럴은 우리가 기존에 알고 있던 '상수'의 다른 이름일 뿐이다.

![capture 117](https://github.com/user-attachments/assets/e71a46dc-159b-40f2-bd3d-3b30cc0c6974)

<br>

## 리터럴의 타입과 접미사

![capture 119](https://github.com/user-attachments/assets/ac5bffc1-536e-4be7-9b61-459769194996)

<br>

## 타입의 불일치

리터럴의 타입은 저장될 변수의 타입과 일치하는 것이 보통이지만, 타입이 달라도 저장범위가 넓은 타입에 좁은 타입의 값을 저장하는 것은 허용된다.

```java
int i = 'B';       // OK
long l = 1234;     // OK
doubld d = 3.14f;  // OK
float f = 3.14;    // 에러. float보다 double타이의 범위가 넓음
```

<br>

## 문자 리터럴과 문자열 리터럴

작은따옴표로 문자 하나를 감싼 것을 '문자 리터럴', 두 문자 이상은 큰 따옴표로 감싸야 하고 '문자열 리터럴'이라 한다.

```java
char ch = 'A';
String name = "Apple";

char ch = '';     // 에러, 문자 리터럴에는 반드시 하나의 문자가 들어가야 함
String anme = ""; // OK. 문자열 리터럴에는 빈 문자열을 허용함
```

<br>

덧셈 이용자를 사용해 문자열을 결합할 수 있다.

```java
3 + " " -> "3" + " " -> "3"
" " + 3 -> " " + "3" -> "3"

문자열 + any type -> 문자열 + 문자열 -> 문자열
any type + 문자열 -> 문자열 + 문자열 -> 문자열
```

<br>

## printf() - 형식화된 출력

printf()는 지시자(specifier)를 통해 변수의 값을 여러 가지 형식으로 변환하여 출력하는 기능을 가지고 있다.

```java
  // age가 27일 때
  System.out.printf("age:%d", age);  // age:27 출력됨.
```

![capture 120](https://github.com/user-attachments/assets/685a4def-de7f-4c20-bd09-2abec93d0a56)



<br>

## Scanner - 화면에서 입력받기

화면으로부터 데이터를 입력받는 기능을 제공하는 클래스이다.

```java
import java.Scanner;  // import문을 추가해 Scanner 클래스를 사용할 수 있도록 해야함.

public class Example {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);  // Scanner 객체를 생성하여 입력을 받을 수 있도록 함
        int number = scanner.nextInt();            // 입력받은 정수를 number에 저장
    }
}
```



<br>

## 형변환

형변환이란, 변수나 상수의 타입을 다른 타입으로 변환하는 것을 말한다. 기본형에서 boolean을 제외한 나머지 타입들은 서로 형변환이 가능하다. 

```java
(타입)피연산자

double d = 123.4;
int number = (int)d;
```

<br>

## 자동 형변환

값의 범위가 작은 타입에서 큰 타입으로의 형변환은 생략할 수 있다. 기존의 값을 최대한 보존할 수 있는 타입으로 자동 형변환된다.

```java
float f = 123;   // float f = (float)123; 과 같음.
```

<br>

![capture 121](https://github.com/user-attachments/assets/db17d1b0-ec78-46fe-886d-557825d9ee71)

위 그림에서, 왼쪽에서 오른쪽으로의 변환은 자동 형변환이 되며, 반대 방향으로의 변환은 형변환 연산자를 사용해야 한다.



<br>



# 3. 연산자



## 연산자와 피연산자

>**연산자(operator)**     : 연산을 수행하는 기호(+,-,*,/) 등
>**피연산자(operand**    : 연산자의 작업 대상(변수, 상수, 리터럴, 수식)



<img width="264" alt="image" src="https://github.com/user-attachments/assets/201f66af-e12f-4eed-94fa-55913b440149">

<br>

## 연산자의 종류

<img width="606" alt="image" src="https://github.com/user-attachments/assets/1b98c609-a67a-446d-84f8-6bdad076d39a">

<br>



## 연산자의 우선순위와 결합규칙

> 1. 산술 > 비교 > 논리 > 대입 순으로 수행된다.
> 2. 단항 > 이항 > 삼항 순으로 수행된다.
> 3. 단항 연산자와 대입 연산자를 제외한 모든 연산의 진행방향은 왼쪽에서 오른쪽이다.



<br>



## 증감 연산자

> **증가연산자(++)** : 피연산자의 값을 1 증가시킴
> **감소연산자(--)**  : 피연산자의 값을 1 감소시킴



```java 
전위형
j = ++i;   //  값이 참조되기 전에 증가시킴

후위형
j = i++;   // 값이 참조된 후에 증가시킴
```



<br>

## 부호 연산자

> \**+** : 피연산자에 1을 곱함
>
> **\-** : 피연산자에 -1을 곱합



<br>

## 논리부정 연산자

> **!** : true는 false로, false는 true로 변환시킨다. 피연산자가 boolean일 때만 사용가능하다.



<br>

## 나머지 연산자

> **%** : 나누기한 나머지를 반환한다. 홀수, 짝수 등 배수검사에 주로 사용된다.



<br>

## 쉬프트 연산자

> **<<, >>, >>>** : 2^n 으로 곱하거나 나눈 결과를 반환한다. 곱셈, 나눗셈보다 빠르다.



<br>

## 비교 연산자

> **>, <, >=, <=, ==, !=** : 피연산자를 같은 타입으로 변환한 후 비교하여 true 또는 false를 반환한다.
> 참조형에는 ==와 !=만 사용할 수 있다.

<br>

## 비트연산자

피연산자를 비트단위로 연산한다.

> **|(OR)** : 피연산자 중 어느 한쪽이 1이면 1
> **&(AND)** : 피연산자 양 쪽 모두 1이면 1
> **^(XOR)** : 피연산자가 서로 다를 때 1



<br>

## 논리연산자

피연산자가 boolean이어야 하며 연산결과도 boolean이다. &&가 ||보다 우선순위가 높다.

> **||(OR)** : 피연산자 중 어느 한쪽이 true이면 true
> **&&(AND)** : 피연산자 양쪽 모두 true이면 true

<br>

## 삼항연산자

조건식의 결과가 true이면 식1의 결과를 반환하고, false이면 식2의 결과를 반환한다.

```java
(조건식) ? 식1: 식2

int number = -5;
String result = (number >= 0) ? "양수" : "음수";  // (number >= 0)가 false이므로 "음수"를 반환
```



<br>

# 4. 조건문과 반복문

조건에 따라 문장을 건너뛰고, 때로는 같은 문장을 반복해서 수행해야할 때, 프로그램의 흐름(flow)를 바꾸는 역할을 하는 문장들을 **'제어문(control statement)'**이라 한다. 제어문에는 **'조건문과 반복문'**이 있다.

<br>

## 조건문 - if

if문은 가장 기본적인 조건문이다. if 다음에 오는 조건식이 참(true)이면 괄호 {} 안의 문장들을 수행한다. 조건식의 결과는 반드시 true 혹은 false이어야 한다.

```java
if (조건식) {
		// 조건식이 참일 때 수행될 문장
}

if (score > 80){
  System.out.println("A등급입니다.")
}
```



<br>

## if - else문

if문에 'else블럭'이 추가된 형태이다. 조건식의 결과가 거짓일 때 else 블럭 내의 문장을 수행한다.

```java
if (조건식) {
  // 조건식이 참일 때 수행될 문장
} else {
  // 조건식이 거짓일 때 수행될 문장
}

if (score==0) {
  System.out.println("점수는 0입니다.")
} else {
  System.out.println("점수는 0이 아닙니다.")
}
```

<br>

## if-else if문

처리해야할 경우의 수가 셋 이상인 경우 'if-else if'문을 사용한다. 결과가 참인 조건식을 만날 때까지 첫 번째 조건식부터 순서대로 평가한다.

```java
if (조건식1) {
  // 조건식1이 참일 때 수행될 문장
} else if (조건식2) {
  // 조건식2가 참일 때 수행될 문장
} else if (조건식3) {
  // 조건식3이 참일 때 수행될 문장
} else {   // 마지막은 보통 else 블록으로 끝나며, 생략 가능.
  // 위의 어느 조건식도 만족하지 않을 때 수행될 문장
}

if (score>=90) {
  grade = 'A';
} else if (score >= 80) {
  grade = 'B';
} else if (score >= 70) {
  grade = 'C';
} else {
  grade = 'D';
}
```



<br>

## 중첩 if문

if문 블럭 내에 또 다른 if문을 포함시키는 것이 가능하다. 내부의 if문은 외부의 if문보다 안쪽으로 들여쓰기를 해서 두 if문의 범위가 명확히 구분될 수 있도록 작성해야 하며, 괄호{}의 생략에 주의해야 한다.

```java
if (조건식1) {
  // 조건식1이 true일 때 수행될 문장들
  if (조건식2) {
    // 조건식1과 조건식2가 모두 true일 때 수행될 문장들
  } else {
    //조건식1이 true이고, 조건식2가 false일 때 수행될 문장들
  }
} else {
  // 조건식1이 false일 때 수행될 문장들
}
```

<br>

## switch문

switch문은  하나의 조건식으로 많은 경우의 수를 처리할 수 있다. 조건식을 먼저 계산한 다음, 그 결과와 일치하는 case문으로 이동하여 문장들을 수행하고 break문이나 switch문의 끝을 만나면 전체 switch문을 빠져나간다.

swit문의 조건식 결과는 정수 또는 문자열이어야 한다. case문의 값은 정수 상수만 가능하며, 중복되지 않도록 한다.

```java
switch (조건식) {
  case 값1:
    // 조건식의 결과가 값1과 같은 경우 수행될 문장
    break;
  case 값2:
    // 조건식의 결과가 값2와 같은 경우 수행될 문장
    break;
  default:
    // 조건식의 결과와 일치하는 case문이 없을 때 수행될 문장
}

switch(month) {
  case 1:
    System.out.println("묵 입니다.");
    break;
  case 2:
    System.out.println("찌 입니다.");
    break;
  case 3:
    System.out.println("빠 입니다.");
    break;
}
```

<br>

# 4-2. 반복문

반복문은 어떤 작업이 반복적으로 수행되도록 할 때 사용되며, for문과 while문, do-while문이 있다.

<br>

## for문

주로 반복 횟수를 알고 있을 때 사용하는 반복문이다. '초기화', '조건식', '증감식', '블럭{}'으로 구성되어 있다. 조건식이 참인 동안 블럭내의 문장들을 반복하다 조건식이 거짓이 되었을 때 반복문을 벗어난다.

![image](https://github.com/user-attachments/assets/4eee255a-2e17-49b5-9bef-28d55cc6059f)

```java
for (초기화;조건식;증감식) {
  // 조건식이 참일 때 수행될 문장들
}

for (int i=1; i<=5; i++) {  // i가 1부터 5까지 1씩 증가하며 "Hello World!"를 5번 출력함.
  System.out.println("Hello World!");
}
```

<br>

## 중첩 for문

for문 안에 또 다른 for문을 포함시키는 것도 가능하다.

```java
for (int i=1; i<=5; i++) {
  for (int j=1; j<=10; j++) {
    System.out.print("*");
  }
  System.out.println();
}

//출력
**********
**********
**********
**********
**********
```

<br>

## 향상된 for문(enhanced for statement)

배열이나 컬렉션에 저장된 요소에 접근할 때 더욱 편리한 방법으로 처리할 수 있도록 JDK1.5부터 향상된 for문이 추가되었다.

```java
for (타입 변수명 : 배열 또는 컬렉션) {
  // 반복할 문장들
}

int[] arr = {10, 20, 30, 40, 50};

for (int tmp : arr) {
  System.out.println(tmp);
}

//출력
10
20
30
40
50
```

<br>

## while문

while문은 조건식이 참인 동안 블럭 내의 문장을 반복한다. 조건식이 거짓이 될 때까지 이 과정이 계속 반복된다. while문의 조건식은 생략불가하다.

![image](https://github.com/user-attachments/assets/8c8a3027-6ec3-41fb-902f-1fa8b9a2b960)

```java
while (조건식) {
  // 조건식의 결과가 참인 동안 반복될 문장들
}

int i = 3;

while (i != 0) {
  System.out.println(i + " - Hello Java!");
  i--;
} 

//출력
3 - Hello Java!
2 - Hello Java!
1 - Hello Java!
```

<br>

## do-while문

기본적인 구조는 while문과 같으나 조건식과 블럭의 순서를 바꿔놓은 것이다. 블럭을 먼저 수행한 후에 조건식을 평가하기 때문에 블럭 내의 문장들이 최소한 한번은 수행될 것을 보장한다.

```java
do {
  // 조건식의 결과가 참일 때 수행될 문장들
} while (조건식);

Scanner scanner = new Scanner(System.in);
int targetNumber = 7; // 맞춰야 할 숫자
int guessedNumber;

System.out.println("숫자 맞추기 게임에 오신 것을 환영합니다!");

do {
	System.out.print("숫자를 맞춰보세요 (1~10): ");
	guessedNumber = scanner.nextInt();

	if (guessedNumber != targetNumber) {
		System.out.println("틀렸습니다. 다시 시도해보세요.");
	}
} while (guessedNumber != targetNumber);

System.out.println("정답입니다!");
```

<br>

## break문

break문은 자신이 포함된 가장 가까운 반복문을 벗어난다. 주로 if문과 함께 사용되어 특정 조건을 만족하면 반복문을 벗어난다.

```java
for (int i=1; i<=10; i++) {
  System.out.println("현재 숫자: " + i);
  
  if (i == 5) {
    System.out.println("숫자 5를 찾았습니다. 반복을 중단합니다.");
    break;
    
    System.out.println("출력이 되는지 확인하는 문장입니다.");  // break문을 만나면 출력되지 않는 문장
  }
}
```

<br>

## continue문

반복이 진행되는 도중에 continue문을 만나면 반복문의 끝으로 이동하여 다음 반복으로 넘어간다. 반복문 내에서만 사용할 수 있다.

```java
for (int i=0; i<=10; i++) {
  
  if (i%2==0) {
    continue;  // 반복문을 벗어나지 않고, 블럭의 끝으로 이동함
  }
  
  System.out.println(i);
}

// 출력
1
3
5
7
9
```



<br>

## 이름 붙은 반복문

중첩 반복문 앞에 이름을 붙이고 break문과 continue문에 이름을 붙여주어서 하나 이상의 반복문을 벗어나거나 건너뛸 수 있다.

```java
outerLoop:
for (int i = 1; i <= 5; i++) {
	for (int j = 1; j <= 5; j++) {
		System.out.println("i: " + i + ", j: " + j);
                
		// 특정 조건에서 외부 반복문을 종료
		if (i * j > 6) {
			System.out.println("i * j가 6을 초과했습니다. outerLoop를 종료합니다.");
				break outerLoop;
		}
	}
}
```

























ㅇ
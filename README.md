# XCode

## 기초사항

- Tokens : 원자, 더이상 쪼갤수 없는 단위, 공백으로 분리할 수 없는 단위 (2 + 3 ;)
  - 각각의 토큰은 공백으로 분리할 수 있음
  - 공백은 탭문자와 줄바꿈 문자가 포함됨
  - 컴파일러는 모든 공백을 하나의 공백으로 처리함
    - Identifiers
    - Keywords : 특정기능을 수행하기 위하여 독점하여 사용하는 단어 (if 를 i   f 와 같이 공백을 추가 하면 더이상 if 키워드가 될수 없음)
    - Punctuations
    - Operatiors
    - Literals
- Expressions :  식, 표현식
  - 하나 이상의 토큰이 모여서, 하나의 값을 도출할 수 있는 식을 표현식이라고 함
  - Evaluate : 표현식을 평가한다라고 함
  - 코드를 실행해서 하나의 결과를 얻는 것이라고 함
  - let x = 7;  (Arithmetic Expression, 산술 표현식)x + 1 ——Evalute—> 8
  - x < 10 : 3개의 표현식으로 논리적인 ( Boolean Expressions, 논리 표현식 )
- Statements : 문장, 구문, 문
  - 표현식이 하나 이상 모여서 실행할 문자

- 리터럴 (Literal) : 코드에서 그 의미가 바뀌지 않고 있는 그대로 사용할 수 있는 값
  - Integer Literals, Floating-point Literals, String Literals, Boolean Literals, nil Literals

e.g. `let x = 7` : 숫자 `7` 이 리터럴, `let` 키워드, 예약어, `x` 식별자, `=` 연산자

- Identifieers : 식별자, 이름, 자료형의 이름, 함수의 이름...
  - 다른 요소와 구별하는 역할
  - 고유해야 함
  - 공백은 허용되지 않음
  - 가독성에 주의해야 함
  - 유니코드를 식별자로 지원

- Keywords : 예약어, 특별한 역할을 위하여 미리 등록된 단어
  - 키워드를 식별자 이름으로 사용해서는 안됨, 이름에 포함된 것은 제외

## Build

```bash

 {code} --- Compile ---> 0101001 --- Link ( Framework ) ---> Executables (Debug, Release Mode)

```

## Link : 실행가능 한 파일 구성

## Compile Time : 빌드 완료까지

## Run Time : 프로그램 실행 환경 시점

## 특수 문자

- Tilde : `~`
- Grave Accent / Back Tick : `
- At Symbol : `@`
- ... `!`
- Sharp / Pound / Hashtag : `#`
- Dollar Sign : `$`
- Percent Sign : `%` 나머지 연산
- Caret : `^` 비트연산
- Ampersand : `&` 메모리 주소연산, 참조전달할 때
- Asterisk ; `*` 곱하기 연산
- Parentheses : `(`  `)` 함수 호출, 연산 순서
- Minus Sign / Hyphen : `-` 빼기 연산
- Underscore : `_`
- Equal Sign : `=` 할당연산, Assignment Operator
- Plus Sign : `+`
- Square Bracket : `[ ]` 대괄호, 꺽쇠, 컬렉션 값에 접근할 때 사용
- Curly Bracket / Brac : `{ }` 코드 블럭
- Backslash : `\` 보간 문자 구성에 사용
- Vertical Bar / Pipe : `|` 비트연산의 논리연산
- Semicolon : `;` 문장의 끝
- Colon : `:` 타입선언
- Comma : `,` 항목을 열거할 때
- Period : `.` 메서드 및 속성을 호출
- Angle Bracket : `< >`
- Slash : `/` 주석, 파일경로, URL
- Question Mark : `?` 옵션널

## 변수 (Variables)

- Syntax : `var varableName = iniialValue` (=> 4개의 토큰의 예시)

## 상수 (Constants)

- Keyword : `let`
- 값을 변경할 수 없음
- 코드가 안전해 짐
- 기본적으로 상수로 선언하고 추후 변경이 필요 할 때 일반 변수로 변경하는 것을 권장

## Nameing Convention (이름 정의 규칙)

- 코드의 가독성이 높아짐
- 강제 규칙은 아님
- Swift 가 채택한 규칙 : `CamelCase`, 낙타 규칙
- UpperCamelCase : 첫번째 단어가 대문자
  - Class
  - Structure
  - Enumeration
  - Protocol
- lowerCamelCase : 첫번째 단어가 소문자
  - Variable
  - Constant
  - Function
  - Property
  - Parameter
- 네이밍 컨벤션을 지키지 않으면 혼동을 유발함을로 반드시 지킴을 원칙

## 코드의 범위 (Scope)

- 동일한 스코프에 접근할 수 있다.
- 글로벌 스코프에서는 선언 순서에 상관없이 접근할 수 있다.
- 로컬 스코프에서 상위 스코프나 글로벌 스코프에 접근 할 수 있다.
- 글로벌 스코프가 아니라면 이미 선언되어 있는 요소에만 접근 할 수 있다.
- 상위 스코프틑 하위 스코프에 접근할 수 없다.
- 서로 다른 스코프에 동일한 이름이 존재한다면 가장 가까운 스코프에 있는 이름을 사용한다.
- 글로벌 스코프가 아닌 다른 모든 스코프는 시작과 끝이 명확해야 한다.

- 기준 : Brace (Curly Bracket) : `Global` `{ Local }` `Global`
  - Global Scope (전역) : 하나만 존재, 어떠한 Brace 에도 속해 있지 않음
  - Local Scope (지역) : 중복으로 존재
  - Declaration Scope

## 메모리의 구조와 크기

- Bit --> YB
- Bit
- Byte : 8Bit, 256가지의 경우의 수 (-128 ~ 127)

- Data Bit
  - `MSB` (Most Significant Bit, 최상위 비트, 가장 왼쪽) : Sign Bit
  - `LSB` (Least Significant Bit, 최하위 비트, 가장 오른쪽)
    - Positive Number (양수) -> MSB (0)
    - Negarive Number (음수) -> MSB (1)

- Signed (부호가 있는 자료형)
  -> -123 --- 0 --- +123

- UnSigned
  -> 0 --- + 255

- 2's Complement (2의 보수 연산 방식으로 양수 음수 처리) : `Bitwise-NOT` + 1 연산
  - 22 -> 00010110
  - Bitwise NOT -> 11101001
  - +1 -> `11101010`
    - Sign Bit (MSB) -> `1`
    - Data Bit -> `1101010`

- Floating-Point
  - `| Sign Bit | Exponent(지수) | Fraction(가수) |`
  - 실수를 저장할 때는 지수와 가수로 나눠서 저장
  - 동일한 메모리 크리에서 정수보다 더 넓은 범위를 저장할 수 있음
  - 부동 소수점에는 오차가 있어서 100% 정확한 값을 저장할 수 없음

## Data Types (자료형)

- Integer Types : 8byte (-900경 ~ + 900경의 정수값)
- Floating-Point Types
- Boolean Types
- Character Types
- String Types

- Built-in (내장) Data Type
- Custom (사용자 정의) Data Type

---

## Number Literals

- 리터널 : 코드에서 의미가 바뀌지 않고 그대로 사용하는 값
- 123, -456, 1.23, 0.567, 1.23E4

## Number Types

## Boolean Types

- Bool

## Strings

-

---

## XCode ShortCuts

- Single Line Comment : `Cmd + /`
- Indent Code : `Cmd + [` or `]`
- Reorder statements : `Alt + Cmd + [` or `]`
- Fold/UnFold class or method body : `Alt + Cmd + left` or `right arrow`
- BreakPoint : `Cmd + \`
- All BreakPoint : `Cmd + Y`
- Completions : `Ctrl + Space`
- Jump to Definition : `Ctrl + Cmd + J` or `Ctrl + Cmd + Click`
- Find any method or function in file : `Ctrl + 6`
- Rename : `Ctrl + Cmd + E`
- Fix : `Ctrl + Alt -> Cmd + F`
- Find in the Project : `Shift + Cmd + F`
- Find Method call hierarchty : `Shift + Ctrl + Cmd + H`
- Jump to Line Number : `Cmd + L`
- Multiple Cursor : `Shift + Ctrl + Click`
- Select All Code : `Cmd + A`
- ReFormat : `Cmd + A` -> `Ctrl+I`
- Refresh Canvas : `Cmd + Option + P`
- Show Library : `Shift + Cmd + L` or `Shift + Option + Cmd + L`

## Refs 1 : [KxCoding](https://www.youtube.com/watch?v=UwHB4sM5tJA)

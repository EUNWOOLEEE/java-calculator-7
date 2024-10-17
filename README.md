# 문자열 덧셈 계산기
## 기능 요구 사항
입력한 문자열에서 숫자를 추출하여 더하는 계산기를 구현한다.
- 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환한다.
  - 예: "" => 0, "1,2" => 3, "1,2,3" => 6, "1,2:3" => 6
- 앞의 기본 구분자(쉼표, 콜론) 외에 커스텀 구분자를 지정할 수 있다. 커스텀 구분자는 문자열 앞부분의 "//"와 "\n" 사이에 위치하는 문자를 커스텀 구분자로 사용한다.
  - 예를 들어 "//;\n1;2;3"과 같이 값을 입력할 경우 커스텀 구분자는 세미콜론(;)이며, 결과 값은 6이 반환되어야 한다.
- 사용자가 잘못된 값을 입력할 경우 IllegalArgumentException을 발생시킨 후 애플리케이션은 종료되어야 한다.

### 입출력 요구 사항

#### 입력
- 구분자와 양수로 구성된 문자열
#### 출력
- 덧셈 결과

```결과 : 6```

#### 실행 결과 예시
```
덧셈할 문자열을 입력해 주세요.
1,2:3
결과 : 6
```

## 프로그래밍 요구 사항
- JDK 21 버전에서 실행 가능해야 한다.
- 프로그램 실행의 시작점은 Application의 main()이다.
- build.gradle 파일은 변경할 수 없으며, 제공된 라이브러리 이외의 외부 라이브러리는 사용하지 않는다.
- 프로그램 종료 시 System.exit()를 호출하지 않는다.
- 프로그래밍 요구 사항에서 달리 명시하지 않는 한 파일, 패키지 등의 이름을 바꾸거나 이동하지 않는다.
- 자바 코드 컨벤션을 지키면서 프로그래밍한다.
  - 기본적으로 Java Style Guide를 원칙으로 한다.

### 라이브러리
- camp.nextstep.edu.missionutils에서 제공하는 Console API를 사용하여 구현해야 한다.
  - 사용자가 입력하는 값은 camp.nextstep.edu.missionutils.Console의 readLine()을 활용한다.

## 기능 목록
- 사용자는 문자열을 입력할 수 있다.
    -  프로그램 실행 시 “덧셈할 문자열을 입력해주세요.” 라는 메시지를 콘솔에 표시한다.
    -  사용자가 입력하는 문자열은 `camp.nextstep.edu.missionutils.Console`의 `readLine()`을 사용하여 받는다.

- 사용자는 기본 구분자(쉼표, 콜론)를 사용하여 숫자를 입력할 수 있다.
    -  사용자가 입력하는 문자열은 유효한 형식이어야 한다.
    -  유효한 형식: 공백 없이 숫자와 구분자가 올바르게 조합되어야 한다.
    -  예외: 유효한 형식이 아닐 경우, `IllegalArgumentException`을 발생시킨 후 종료한다.

-  사용자는 커스텀 구분자를 사용하여 숫자를 입력할 수 있다.
    -  사용자가 입력하는 문자열은 유효한 형식이어야 한다.
    -  유효한 형식: `//`와 `\n` 사이에 구분자가 위치하고, 이어서 공백 없이 숫자와 구분자가 올바르게 조합되어야 한다.
    -  예외: 유효한 형식이 아닐 경우, `IllegalArgumentException`을 발생시킨 후 종료한다.

-  문자열에서 숫자 추출하여 결과 값을 계산한다.
    -  구분자를 기준으로 숫자를 추출하여 변수 `res`에 더한다.

-  결과 값을 출력한다.
    -  합산이 끝난 값을 콘솔에 “결과 : `res`” 형식으로 표시한다.

## 플로우차트
![calculator](https://github.com/user-attachments/assets/669813f8-983c-438b-8377-8b1a1326cb1a)
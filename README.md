# # 프리코스 2주차 미션 - 자동차 경주 게임

***

## 기능 목록

### 입력 받기
- `경주할 자동차 이름을 입력하세요. (입력 완료: 0) : ` 메시지를 출력한다.
- 자동차 이름을 입력 받는다.
    - 1대씩 입력 가능
    - 여러 대 입력 가능 (쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능)
    - 알파벳 또는 알파벳+숫자로 구성 (숫자로 시작 불가)
    - 공백 불가
    - 최대 5개의 이름 입력 가능
    - 동일한 이름에 대해 입력 순서대로 숫자를 붙여 구분 (예시 → `pobi1`, `pobi2`)
- `시도할 횟수를 입력하세요. : ` 메시지를 출력한다.
- 1 이상의 정수를 입력받는다.

### 게임 실행
- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
    - 출력 예시 → `pobi : --    woni : ----   jun : ---`
- 전진하는 조건은 0에서 9 사이에서 무작위 값을 구한 후 무작위 값이 4 이상일 경우이다.
- 사용자가 잘못된 값을 입력할 경우 `IllegalArgumentException`을 발생시킨 후 애플리케이션은 종료된다.

### 게임 종료
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
    - 우승자 출력 예시 → `최종 우승자 : pobi`
- 우승자가 여러 명일 경우 쉼표(,)를 이용하여 구분한다.
  - 공동 우승자 출력 예시 → `최종 우승자 : pobi, jun`

### 예외 처리
- 공통: 메시지를 출력하며 종료한다. 
- 이름 입력
  - 이름에 아무것도 입력하지 않은 경우: `이름을 입력해 주세요.`
  - 쉼표(,)가 아닌 다른 구분자를 사용한 경우: `이름은 쉼표(,)로 구분해 주세요.`
  - 이름이 5자 초과인 경우: `각 이름은 5자 이하로 입력해야 합니다.`
  - 이름 입력 시 알파벳 또는 숫자 외의 문자를 사용한 경우: `이름은 알파벳과 숫자만 포함해야 합니다.`
  - 이름 시작이 숫자일 경우: `이름의 시작은 알파벳이어야 합니다.`
  - 이름에 공백만 포함된 경우: `이름에는 공백만 입력할 수 없습니다.`
  - 이름의 개수가 5개가 초과일 경우: `최대 5대의 자동차만 입력할 수 있습니다.`

- 시도 횟수 입력
   - 시도 횟수가 0 또는 음수를 입력한 경우: `시도 횟수는 1 이상의 정수로 입력해야 합니다.`
   - 시도 횟수에서 정수 이외의 값을 입력한 경우: `정수로만 입력해 주세요.`

***

## 프로그래밍 요구 사항 
### 기본 요구 사항
- JDK 21에서 실행 가능해야 한다.
- `Application` 클래스의 `main()` 메서드에서 시작한다.
- 제공된 `build.gradle` 파일을 변경할 수 없다. 외부 라이브러리는 사용하지 않는다.
- 프로그램 종료 시 `System.exit()`를 호출하지 않는다.
- 요구 사항에 명시되지 않는 한, 파일이나 패키지의 이름을 바꾸거나 이동하지 않는다.
- 자바 코드 컨벤션을 준수하며, 기본적으로 Java Style Guide를 따른다.

### 프로그래밍 규칙
- 인덴트 깊이는 최대 2까지만 허용된다.
- 3항 연산자를 사용하지 않는다.
- 함수(또는 메서드)는 한 가지 일만 하도록 최대한 작게 만든다.
- JUnit 5와 AssertJ를 이용하여 기능 목록이 정상적으로 작동하는지 테스트 코드로 확인한다.

### 라이브러리 사용
- **필수 라이브러리**: `camp.nextstep.edu.missionutils`의 `Randoms` 및 `Console` API 사용
    - **Random 값 추출**: `camp.nextstep.edu.missionutils.Randoms`의 `pickNumberInRange()` 메서드 사용
    - **사용자 입력**: `camp.nextstep.edu.missionutils.Console`의 `readLine()` 메서드 사용


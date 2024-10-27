# 자동차 경주

### 게임 설명

- 여러 대의 자동차가 주어진 횟수 동안 전진 또는 멈춘다.
- 각 자동차에는 이름이 있으며, 각 횟수마다 자동차 이름과 함께 결과가 출력된다.

### 규칙

1. **자동차 이름 입력**: 쉼표(,)로 구분하여 입력하며, 이름은 5자 이하만 가능하다.
2. **이동 횟수 입력**: 사용자가 게임의 이동 횟수를 입력한다.
3. **전진 조건**: 각 이동 시 0에서 9 사이의 랜덤 값을 생성하여 4 이상일 경우 전진한다.
4. **우승자 판정**: 가장 멀리 간 자동차가 우승하며, 공동 우승자가 있을 수 있다.
5. **에러 처리**: 잘못된 입력 시 `[ERROR]`로 시작하는 메시지와 함께 애플리케이션이 종료된다.

### 우승자 출력

- 최종 우승자가 한 명일 경우: `최종 우승자 : 자동차 이름`
- 최종 우승자가 여러 명일 경우: `최종 우승자 : 자동차 이름, 자동차 이름, ...`

## 프로세스

1. 애플리케이션 실행
   - `경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)` 출력 + 입력 대기
2. 입력 (쉼표(,)를 기준으로 분리한 후 자동차 이름에 대해 앞뒤 공백 제거)
   - 검증
     1. 자동차 이름이 빈 문자열인 경우
     2. 이름이 1자 이상 5자 이하로 이루어져있는지 확인
     3. 자동차 이름이 중복되는지 확인
     4. 자동차 갯수가 최소 2대이상인지 확인
   - 불만족시: `[ERROR]` 출력 + 애플리케이션 종료
3. `시도할 횟수는 몇 회인가요?` 출력 + 입력 대기
   - 검증
     1. 시도할 횟수가 빈 문자열인지 확인
     2. 1이상의 숫자(정수)로 이루어져있는지 확인
   - 불만족시: `[ERROR]` 출력 + 애플리케이션 종료
4. 반복 (입력한 시도 횟수만큼)
   1. 컴퓨터의 숫자 생성 (0~9 랜덤 생성)
   2. 판정
      1. 자동차 전진 가능 여부 확인
      - 무작위 값이 4이상 => true
      - 무작위 값이 3이하 => false
      2. 자동차 전진 횟수 업데이트
      - true이면 1칸 전진
      - false이면 제자리
   3. 판정 결과 출력
      - `자동차 이름 : 전진한 거리(예: ---)`
5. 우승자 안내 문구
   - 판정: 가장 멀리 간 자동차가 우승
     - 단독 우승자일 경우 `최종 우승자 : 자동차 이름` 출력 + 애플리케이션 종료
     - 공동 우승자일 경우 `최종 우승자 : 자동차 이름, 자동차 이름, ...` 출력 + 애플리케이션 종료

## 예외처리

자동차 입력값

- 자동차 이름이 빈 문자열인 경우
- 자동차 이름이 1~5글자로 이루어지지 않은 경우
- 자동차 이름이 중복되는 경우
- 자동차 갯수가 1개인 경우 (최소 2대이상)

시도 횟수

- 빈 문자열인 경우
- 숫자가 아닌 값으로 입력될 경우
- 양수가 아닌 경우

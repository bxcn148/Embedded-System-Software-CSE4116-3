Download link :https://programming.engineering/product/embedded-system-software-cse4116-%ea%b3%bc%ec%a0%9c-3/


# Embedded-System-Software-CSE4116-3
Embedded System Software [CSE4116] 과제 3
목표

Module programming, 디바이스 드라이버 구현, interrupt 등, 배운 내용을 활용하여 간단한 stopwatch 프로그램을 작성한다.

구현

fpga_fnd device driver 와 interrupt 를 포함한 stopwatch 기능을 가진 하나의 모듈로 구현한다. Interrupt 사용 시 top half interrupt 와 bottom half interrupt 로 나누어 구현하고,

보고서에 top half routine 과 bottom half routine 으로 구분한 명확한 기준을 제시한다.

강의 자료및 수업 내용에 근거하여 자유롭게구현하면 됩니다.

이와 관련하여아래 사항들의 경우 감점 대상입니다.

Top & bottom half routine 으로 나누어 구현하지 않은 경우

하드웨어버튼입력 시즉각적으로 수행되어야 하는 부분이 제대로 동작하지않을 경우 (3.기능 항목에서 파란색 글씨로 명시된 내용에 주의)

module 을 실행시키는 application 을 구현한다. (parameter 없음)

기능

fpga_fnd(FND) : 앞의 두 자리는 분(60 분), 뒤의 두 자리는 초(60 초)를 표시한다.

FND 초기 상태: 0000

1 초마다 FND 의 정보를 갱신 (timer 사용)

fpga_dot (Dot) : 1/10 초를 표시한다. (0~9)

아래 기능 키 입력은 interrupt 를 이용하여 수행한다.

Home 버튼 : start 스톱워치 시작

Back 버튼 : pause 일시 정지

입력 시 소수점 1 번째 자리까지의 시간이 유지되어야 한다.

• E.g. 4.5 초에 일시 정지 버튼 눌렀다가 다시 시작 시 1 초가 아닌 0.5 초 후에 5 가 출력되어야 함

VOL+ 버튼 : reset FND, Dot Matrix 출력 및 시간이 모두 초기 상태로 돌아간다.

VOL- 버튼 : stop 3 초 이상 누르고 있을 시 어플리케이션을 종료

(즉, user application 은 해당 버튼을 눌러 종료될 때까지 끝나지 않음)

프로그램 종료시 FND 는 0000 으로, Dot 는 Off 상태로 초기화한다.

디바이스 드라이버의 이름은 /dev/stopwatch 로 통일한다. (major number : 242)

응용 프로그램은 sleep 상태로 대기하며 구현 방법은 자유롭게 하되, 구현 내용을 보고서에 명시해야 한다.



Embedded System Software 2 / 2



제출방법

아래 제출파일을 사이버 캠퍼스에 업로드

[프로그램 제출란]

소스코드, Makefile, Readme 파일을 모두 포함한 [HW3]학번.tar.gz Ex) [HW3]20240000.tar.gz

소스코드구분

app 폴더 (소스코드, Makefile)

module 폴더 (소스코드, Makefile)

Readme (driver 의 name 과 major number 를 반드시 포함)

파일 압축방법 : 학번 폴더를생성하고, 그 안에 숙제관련 폴더(파일)을저장한뒤, 학번폴더가있는 위치에서 tar –cvzf [HW3]학번.tar.gz ./학번폴더

[보고서제출란]

[HW3]학번_reprt.pdf

Ex) [HW3]20240000_report.pdf

제공되는보고서형식참고. 세부 목차/내용 추가가능.

본인의 응용 프로그램과 ioctl 동작을 설명하는 Flowchart 가 반드시 포함되어야 함.

보고서는반드시 PDF로 제출

Due Date : 프로그램 – 2024 년 6 월 2 일 일요일 23:59

보고서 – 2024 년 6 월 4 일 화요일 23:59

평가 내용

프로그램 100점(주석 점수포함), 보고서 20점.

Late : 하루에 10% 감점

Due Date 기준 프로그램은 +5 일까지, 보고서는 +3 일까지.

제출 형식틀린경우 5% 감점.

Copy 적발 시 0 점.

Copy 의심자는 조교와 면담을 통해 소명해야 함.

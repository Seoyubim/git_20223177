#  리눅스 명령어와 vim 에디터에서 매크로 관련하여 조사


### 리눅스 명령어: top, ps, jobs, kill 명령어 조사하기

1) top:
   * 시스템의 사용량, 시스템의 상태(CPU, Memory, Process)를 실시간으로 파악 가능하게 해준다.
   * 사용법은 리눅스에서 top (옵션)을 치고 들어가면 된다.
   * 옵션
      | 옵션 | 설명 |
      | :---: | ---- |
      | -b | batch 모드로 정보를 화면에 일렬로 출력 |
      | -d delay | 지정한 시간(초)의 간격으로 정보를 업데이트하여 출력 |
      | -p pid | 지정한 프로세스 ID(pid)의 정보만을 출력 |
      | -q | 시간 간격 없이 계속해서 업데이트 정보 출력 |
   * top 실행 후 단축키 명령어
      | 명령어 | 설명 |
      | :---: | --- |
      | space | 정보를 업데이트 |
      | shift + p | CPU 사용률이 높은 프로세스 순서대로 표시 |
      | shift + m | 메모리 사용률이 높은 프로세스 순서대로 표시 |
      | shifr + t | 프로세스가 돌아가고 있는 시간 순서대로 표시 |
      | k | 프로세스를 종료시킴 |
      | h | 도움말 |
      | q | top을 종료시킴 |
    * 첫 번째 줄: 서버 정보
    * 두 번째 줄: 프로세스 정보
    * 세 번째 줄: CPU 정보
    * 네 번쨰, 다섯 번쨰 줄: 메모리 정보
    
    <img src="https://user-images.githubusercontent.com/106818132/171907650-d5252386-e47e-4911-b08b-b6cda69745c4.jpg" width="500" height="300">

   
2) ps:
   * Process status로 현재 실행중인 프로세스 목록과 상태를 보여준다. 
   * 사용법은 리눅스에서 ps (옵션)을 치고 들어가면 된다. 
   * top 실행 후 단축키 명령어
      | 옵션 | 설명 |
      | :---: | --- |
      | -A | 모든 프로세스 출력 |
      | -e | 커널 프로세스를 제외한 모든 프로세스 출력 |
      | -a | 세션 리더와 터미널과 연관된 프로세스들을 제외한 모든 프로세스 보여줌 |
      | -f | 풀 포맥으로 보여줌 |
      | -M | 64비트 프로세스들을 보여줌 |
      | -p | 특정 PID를 지정할 떄 사용 |
      | -r | 현재 실행 중인 프로세스 보여줌 |
      | -u | 특정 사용자의 프로세스 정보를 확인할때 사용 |
   * 항목
      | 항목 | 설명 |
      | :---: | --- |
      | TIME | 총 CPU 사용 시간 |
      | PID | 프로세스의 식별번호 |
      | PPID | 부모 프로세스 ID |
      | %CPU | CPU 사용 비율의 추정치 |
      | %MEM | 메모리 사용 비율의 추정치 |
      | TTY | 프로세스와 연결된 터미널 |
      
3) jobs:
   * 작업의 상태, 작업목록(작업번호, 상태, 명령어)을 표시하는 명령어로 현재 쉘 세션에서 실행시킨 백그라운드 작업의 목록이 출력된다.
   * 작업번호는 PID와는 달리, 별도로 부여되는 백그라운드 작업목록 상의 번호이다.
   * 사용법은 리눅스에서 jobs (옵션) [job ID]을 치고 들어가면 된다. 
   * 옵션
      | 옵션 | 설명 |
      | :---: | --- |
      | -l | 프로세스 그룹 ID를 state 필드 앞에 출력 |
      | -n | 프로세스 그룹 중에 대표 프로세스 ID를 출력 |
      | -p | 각 플세스 ID에 대해 한 행씩 출력 |
   * jobs로 알 수 있는 세션의 상태 값
      | 상태 | 설명 |
      | :---: | --- |
      | Running | 작업이 일시 중단되지 않았고 종료하지 않고 계속 진행 |
      | Done | 작업이 완료되어 0을 반환하고 종료 했음 |
      | Done(code) | 작업이 정삭적으로 완료되었으며, 0이 아닌 코드를 반환 했음|
      | Stopped | 작업이 일시 중단 |
      | Stopped(SIGTSTP) | SIGTSTP 신호가 작업을 일시 중단 |
      | Stopped(SIGSTOP) | SIGSTOP 신호가 작업을 일시 중단 |
      | Stopped(SIGTTIN) | SIGTTIN 신호가 작업을 일시 중단 |
      | Stopped(SIGTTOU) | SIGTTOU 신호가 작업을 일시 중단 |
      
4) kill:
   * 프로세스를 종료할 때 사용하지만 내부적으로는 프로세스에 시그널을 보내 원하는 작업을 하게 한다.
   * kill (옵션 또는 시그널) PID를 입력하면 된다. 
   * 시그널(Signal)은 키보드 인터럽트나 에러 상황이 일어났을 때 발생, 쉘이 자식 프로세스에 작업 명령을 보낼 때에도 사용한
   * 시그널의 목록은 kill -l(엘) 명령으로 확인할 수 있다.
   
   <img src="https://user-images.githubusercontent.com/106818132/172007867-690f5121-f13d-4279-aafe-2b24089aef90.png" width="500" height="300">
   * 옵션
      | 옵션 | 설명 |
      | :---: | --- |
      | pid... | 종료 시킬 프로세스 ID나 프로세스 이름을 지정 |
      | -s | 전달할 시그널의 종류를 지정. 시그널 이름이나 번호를 써줌 |
      | -l | 시그널로 사용할 수 있는 이름들을 출력, signal의 종류를 출력 |
      | -1 | -HUP 프로세스를 재활성화 |
      | -9 | 프로세스를 강제로 종료 |
   * Kill 명령으로도 종료되지 않는 프로세스는 -9옵션을 이용하여 강제종료 시킨다. 
   * 보통 ps 명령어를 이용해서 종료시킬 프로세스 정보를 확인한다.

---
### vim 에디터에서 매크로 사용방법에 대하여 조사하기(q, @)

* Macro는 Vim 명령어들을 기록하고, 이를 반복할 수 있는 기능이다.
* 레지스터 주소는 매크로명으로 a ~ z 사용 가능하다.
* 종류
  * `q{레지스터}` 로 매크로 기록 시작
  * `q` 로 매크로 기록 종료
  * `@{레지스터}` 로 저장된 매크로 실행
  * `@@` 로 직전에 실행한 매크로 재실행
  * `{반복횟수}@{레지스터}` 또는 `{반복횟수}@@` 로 저장된 매크로를 '반복횟수' 만큼 재실행
* 순서
  * 매크로 기록하는 방법은 q{레지스터} -> 작업 -> q
  * 레코딩 끝난 후 기록된 내용 보려면 reg명령을 이용하면 된다. :reg {레지스터}
  * 매크로 실행은 q{레지스터}, 3회 반복을 실행은 3q{레지스터}이다.

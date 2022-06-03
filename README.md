#  리눅스 명령어와 vim 에디터에서 매크로 관련하여 조사


### 리눅스 명령어: top, ps, jobs, kill 명령어 조사하기

1) top:
   * 시스템의 사용량, 시스템의 상태(CPU, Memory, Process)를 실시간으로 파악 가능하게 해준다.
   * 리눅스에서 top (옵션)을 치고 들어가면 된다.
   * 
2) ps:
   * Process status로 현재 실행중인 프로세스 목록과 상태를 보여준다. 
   * 리눅스에서 ps (옵션)을 치고 들어가면 된다. 
   * 
3) jobs:
   * 작업의 상태를 표시하는 명령어로 현재 쉘 세션에서 실행시킨 백그라운드 작업의 목록이 출력된다.
   * 
4) kill:
   * 프로세스를 종료할 때 사용하지만 내부적으로는 프로세스에 시그널을 보내 원하는 작업을 하게 한다.
   * kill (옵션 또는 시그널) PID를 입력하면 된다. 
   * 

---
### vim 에디터에서 매크로 사용방법에 대하여 조사하기(q, @)

* Macro는 Vim 명령어들을 기록하고, 이를 반복할 수 있는 기능이다.
* 레지스터 주소는 매크로명으로 a ~ z 사용 가능하다.
* 

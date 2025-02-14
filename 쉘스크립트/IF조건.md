## IF 조건
```bash
if [ 조건문 1 ]; then
    - 조건문1이 참일 경우 실행할 명령어

elif [ 조건문 2 ]; then
    - 조건문1이 거짓이고 조건문2가 참일 경우 실행할 명령어

else
    - 조건문1, 2가 모두 거짓일 경우 실행할 명령어

fi
```

<br>

## 비교표
|숫자 비교문||문자 비교문||파일 비교문||
|---|---|---|---|---|---|
|A -eq B|A와 B가 같은가?|A = B|문자 A와 B가 같은가?|-d file|파일이 존재하고 디렉토리인가?|
|A -ge B|A와 B가 크거나 같은가?|A != B|문자 A와 B가 다른가?|-e file|파일이 존재 하는가?|
|A -gt B|A가 B보다 큰가?|A < B|문자 A가 B보다 작은가?(바이트)|-f file|파일이 존재하고 파일인가?|
|A -le B|A가 B보다 작거나 같은가?|A > B|문자 A가 B보다 큰가?(바이트)|-r file|파일이 존재하고 읽을 수 있는가?|
|A -lt B|A가 B가 작은가?|-n A|A의 문자열의 길이가 0보다 큰가?|-s file|파일이 존재하고 비어있지 않은가?|
|A -ne B|A와 B가 같지 않은가?|-z A|A의 문자열의 길이가 0인가?|-w file|파일이 존재하고 쓰기가 가능한가?|

### 예시1 (숫자 비교문)
```bash
vi la.sh

----------------------------
#!/bin/bash
LOAD=$(로드 에버리지 숫자를 가져오는 명령)

if ["${LOAD}" -ge 5]; then
    슬랙/텔레그램/메일로 경고메세지를 날리는 명령
else
    echo "No Problem"
fi
----------------------------
```

### 예시2 (문자 비교문)
```bash
vi str.sh

if [ a == a ]; then
    같을 때 실행할 명령
else 
    다를 때 실행할 명령
fi
```

### 예시3 (파일 비교문)
```bash
vi nginx_stop.sh

----------------------------
#!/bin/bash

## nginx stop할 때의 로직
PID="/run/nginx.pid"

if [ -e "${PID}"]; then
    kill로 nginx의 pid번호를 읽어서 죽이는 명령
else
    echo "nginx not running"
fi
----------------------------
```

### 예시4 (호스트 네임 확인)
* server1 (웹서버)
* server2 (DB 서버)
* server3 (스토리지 서버)
  
```bash
vi server_check.sh

#!/bin/bash

S_NAEM=$(hostname)

if [ "$S_NAME" = "server1"]; then
    echo "웹서버입니다"
else
    echo "웹서버가 아닙니다"
fi
```

### 예시5 (복합)
```bash
vi composite.sh

## AND 조건(-a)
[ 조건1 -a 조건2 -a 조건3 ]

## OR조건 (-o)
[ 조건1 -o 조건2 -o 조건3 ]

## 복합 조건
[ 조건1 -a 조건2 -o 조건3 ]
```
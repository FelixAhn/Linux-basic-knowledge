## CASE 조건
```bash
case 변수 in
    패턴1)
        패턴1이 참일 경우 실행할 명령어;;

    패턴2)
        패턴2이 참일 경우 실행할 명령어;;

    *)
        위에서 지정한 모든 패턴에 해당이 안되는 경우 실행할 명령어;;
esac
```

<br>

### 예시 (웹서버 컨트롤 스크립트)
```bash
vi nginx_ctl.sh

#!/bin/bash

## ./nginx_ctl.sh start       :  nginx start
## ./nginx_ctl.sh stop        :  nginx stop
## ./nginx_ctl.sh reload      :  nginx reaload
## ./nginx_ctl.sh configtest  :  nginx.conf의 문법을 확인

### 파라미터 인식
### ./nginx_ctl.sh a b c
### $1 : a, $2 : b, $3 : c

CMD = $1

case "${CMD}" in
start)
    nginx 시작하는 명령어;;
stop)
    nginx 중단하는 명령어;;
reload)
    nginx 리로드하는 명령어;;
configtest)
    nginx 설정파일을 확인하는 명령어;;
*)
    echo "사용방법 : ./nginx_ctl./sh {start|stop|reload|configtest}";;
esac
```

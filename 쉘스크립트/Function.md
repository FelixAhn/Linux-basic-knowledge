## 함수
```bash
function 함수명 {
    명령어
}
```
### 배열
```bash
배열에 숫자 또는 문자 사용 가능
```

### 리다이렉션
```bash
입력/출력/에러(표준 스트림)를 지정한 곳으로 바꿔줌
쉘 스크립트 안에서 텍스트 파일을 활용
```

### 예제
```bash
vi ex.sh

#!/bin/bash

function line {
    echo "======================="
}

line
echo "df result"
line
df -h
line
echo "free result"
line
free -m
line

chmod 700 ex.sh
```

### 예제 (계산 모음)
```bash
vi calc.sh

function plus {
    echo "$1 + $2 = "
    echo $[ $1 + $2 ]
    echo
}

function minus {
    echo "$1 - $2 = "
    echo $[ $1 - $2 ]
    echo
}

function mult {
    echo "$1 * $2 = "
    echo $[ $1 * $2 ]
    echo
}

function div {
    echo "$1 / $2 = "
    if [ $2 - eq 0]
    then
        echo "0으로 나눌 수 없음"
    else
        echo $[ $1 / $2 ]
    fi
    echo
}
```

### 예제 (계산 모음 이용)
```bash
vi calc_use.sh

#!/bin/bash

source ./calc

plus 30 40
minus 10 3
mult 11 7
div 2 0 
div 14 2

chmod 700 use_calc.sh
```



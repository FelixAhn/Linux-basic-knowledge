## redirection 
```bash
표준 스트림 (stdin, stdout, stederr)을 부등호를 사용하여 지정한 위치로
보낼 수 있는 방향지정 옵션

- > : 출력 결과를 파일에 쓰기 (기존 내용 덮어쓰기)
    - 예: echo "Hello, World!" > output.txt
- >> : 출력 결과를 파일에 추가 (기존 내용 유지)
    - 예: echo "Append this line" >> output.txt
- 2> : 오류 메시지(stderr)를 파일에 저장
    - 예: ls nonexistentfile 2> error.log
- 2>> : 오류 메시지(stderr)를 파일에 추가
    - 예: ls nonexistentfile 2>> error.log
- &> : 표준 출력(stdout)과 오류(stderr)를 동시에 파일에 저장
    - 예: command &> output.log
- < : 파일을 입력으로 사용
    - 예: cat < input.txt
- | : 명령의 출력 결과를 다른 명령의 입력으로 전달 (파이프)
    - 예: ls | grep ".txt"
```

## echo
```bash
문자열을 출력하는 도구

- echo [문자열] : 지정한 문자열 출력
    - 예: echo "Hello, World!"
- echo -n [문자열] : 출력 뒤에 개행을 생략
    - 예: echo -n "No newline"
- echo -e [문자열] : 이스케이프 시퀀스를 해석하여 출력
    - 예: echo -e "Line1\nLine2\tTabbed"
```

## chmod (Change Mode)
```bash
파일이나 디렉토리의 모드(접근 권한)을 변경하는 도구

- chmod [권한] [파일명] : 권한 설정
    - r : 읽기 (4)
    - w : 쓰기 (2)
    - x : 실행 (1)
- chmod 755 [파일명] : 소유자는 rwx, 그룹과 다른 사용자에게는 rx 권한 부여
- chmod u+x [파일명] : 소유자에게 실행 권한 추가
- chmod g-w [파일명] : 그룹의 쓰기 권한 제거
- chmod o=r [파일명] : 다른 사용자에게 읽기 권한만 부여
```

## chown (Change the Owner of a file)
```bash
파일의 소유권을 바꾸기 위한 도구

- chown [소유자] [파일명] : 파일 소유자 변경
    - 예: chown user1 myfile.txt
- chown [소유자]:[그룹] [파일명] : 파일 소유자와 그룹 변경
    - 예: chown user1:group1 myfile.txt
- chown -R [소유자] [디렉토리] : 디렉토리와 하위 항목의 소유자 변경
    - 예: chown -R user1 /mydir
```

## sudo (Superuser DO => Substitude User DO)
```bash
root 사용자의 보안 권한을 이용하여 명령 또는 프로그램을 실행하는 도구

- sudo [명령어] : 명령을 관리자 권한으로 실행
    - 예: sudo apt update
- sudo -l : 현재 사용자에게 허용된 명령어 목록 확인
- sudo su : 관리자 계정으로 전환
```

## who
```bash
현재 시스템에 로그인한 사용자 목록을 출력

- who : 사용자 목록 출력
- w : 사용자와 관련된 상세 정보 출력 (로그인 시간, 사용 중인 터미널, 실행 중인 명령 등)
```
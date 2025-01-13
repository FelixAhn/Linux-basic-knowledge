## AND 조건 ( && )
```bash
AND 연산의 "하나라도 거짓이면 전체 결과가 거짓"이라는 특성이용
AND 좌측 명령/테스트의 결과가 참이면 우측 명령 실행 (우측이 참인지 판단 해야하기 때문)
AND 좌측 명령/테스트의 결과가 거짓이면 우측 명령을 실행하지 않음 (이미 거짓이므로)

test 1 == 1 && echo "This is True"
[ 1 == 1 ] && echo "This is True"
: This is True

test 1 == 2 && echo "This is True"
: 아무것도 출력 x
```

## OR 조건 ( || )
```bash
OR 연산의 "하나라도 참이 있으면 전체 결과가 참"이라는 특성이용
OR 좌측 명령/테스트의 결과가 참이면 우측 명령을 실행하지 않음 (이미 참이므로)
OR 좌측 명령/테스트의 결과가 거짓이면 우측 명령을 실행 (우측이 참인 판단해야 하기 때문)

test 1 == 2 || echo "This is False"
[ 1 == 2 ] || echo "This is False"
: This is False

[ 1 == 1 ] || echo "This is False"
: 아무 것도 출력 x
```
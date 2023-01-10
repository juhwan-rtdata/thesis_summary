## git 계정 연동
- 현재 로그인된 계정 확인 : git config user.name, git config user.email

- 변경하고자 하는 이름, 계정 입력
  - git config --global user.name
  - git config --global user.email

## git 원격 저장소 연동
- 커맨드라인에서 원격 저장소 푸시
  - git remote add origin <깃허브주소>
  - 원격 저장소에 origin을 추가(add)하겠다고 깃에서 알려줌
    - 원격 저장소 -> remote, 깃허브 저장 주소 -> origin
- 원격 저장소 연결 확인
  - git remote -v
- 원격 저장소 

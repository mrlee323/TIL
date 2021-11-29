# github로 push하기
- 터미널에서 작업한 파일을 git 저장소로 push하기

## 터미널에서 파일 작업하기
- vi 파일명 -> vim으로 이동후 파일을 수정
- vsc를 이용해 파일 수정도 가능

## 파일 작업 완료 후
- git add 파일명 -> 파일을 staging Area로 보냄 commit 전단계
- git commit 파일명 -> local 저장소로 저장 
  - 저장시 vim모드가 뜨고 거기에 commit에 대한 정보를 기입
- git push origim main -> github로 push/ 여기서 main은 branch name
- __명령어 한개 끝날때마다 git status로 작업상황을 확인__

## 원격저장소에서 파일 내려받기

- git pull origin master or git pull 입력

- 내려받기후 git log와 ls로 상태 확인


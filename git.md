# git 명령어

- git init : git 생성
- git config --global user.name `"이름"` : git 계정 name 등록
- git config --global user.email `"이메일"` : git 계정 이메일 등록

* git add `파일명` : 해당 파일 추적
* git add -A : 모든 파일 추적

- git commit : 변경 내용 확정
- git commit -m `"설명"` : 변경 내용을 설명과 함께 확정

* git log : commit 히스토리 조회
* git log --graph --all --decorate : 모든 분기의 commit 히스토리 조회
* log --all --decorate --oneline --graph : 모든 분기의 commit 히스토리 한 줄로 조회
  - git config --global alias.`별칭` "log --all --decorate --oneline --graph" : 별칭 지정
  - git `별칭` : 확인

- git status : 현재 저장소 내의 파일 상태 확인
- git reset `log의 앞 6자리` --hard : 해당 commit 이후의 이력 모두 삭제
- git revert `log의 앞 6자리` --hard : 해당 commit까지 되돌린 것을 commit하여 기록 남김

* git branch : 브랜치 목록 확인
* git branch `브랜치명` : 브랜치 생성
* git checkout `브랜치명` : 해당 브랜치로 이동
* git merge `가져올 것이 있는 브랜치명` : 다른 브랜치에 있는 변경 내용을 현재 브랜치에 병합 (모든 로그 남아있음, 여러 줄)
* git rebase `가져올 것이 있는 브랜치명` : 다른 브랜치에 있는 변경 내용을 현재 브랜치에 재정렬하여 병합 (한 줄)
* git branch -D `지울 브랜치명` : 해당 브랜치 삭제
* git branch -d `지울 브랜치명` : (변경사항이 없는 경우에만) 해당 브랜치 삭제

- git remote : 현재 프로젝트의 원격 저장소 확인
- git remote add `원격명` `주소` : 새로운 원격 저장소 등록
- git push -u `원격명` `브랜치명` : add하고 commit한 코드 git server에 보내기 (-u : 자동연결)
- git push -d `원격명` `브랜치명` : 원격 브랜치 삭제

* git clone `주소` : 원격 저장소 복제
  - cd `폴더명` : 해당 폴더에서 작업하려면 change directory

- git fetch : 원격 저장소로부터 필요한 파일을 다운 (병합은 따로 해야 함)
  - git merge origin/master : origin이라는 이름의 원격 repo의 master 브랜치 내용을 fetch된 상태에서 현재 로컬로 병합
- git pull `원격명` `브랜치명` : 원격 저장소로부터 필요한 파일을 다운 + 병합

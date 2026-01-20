# Git Remote

Git : 프로그램

---

## 원격 저장소

: 코드와 버전 관리 이력을 온라인 상의 특정 위치에 저장하여 개발자가 협업하고 코드를 공유하는 저장 공간

- GitLab
- GitHub
- Bitbucket

## Remote

### git remote add origin (remote_repo_url)

- 로컬 저장소에 원격 저장소 주소 등록
- git remote :  로컬 저장소에 원격 저장소 추
- origin : 추가하는 원격 저장소 별칭
- remote_repo_url : 추가하는 원격 저장소의 주소

### git remote -v

- 등록된 원격 저장소 목록 확인

---

## Push

### git push origin master

- 원격 저장소에 commit 목록을 업로드

### 변경 후 수정 과정

1. git add (파일 이름)
2. git commit -m ‘(커밋 이름)’
3. git push origin master
- commit 이력이 없다면 push도 불가

---

## Push / Pull & Clone

### git pull origin master

- 원격 저장소의 변경사항만을 받아옴 → 업데이트
- origin이라는 원격에서 master라는 것을 받아옴

### git clone (remote_repo_url)

- 원격 저장소 전체를 복제 → 다운로드
- clone 받은 프로젝트는 이미 git init 되어있음

---

## gitignore

- Git에서 특정 파일이나 디렉토리를 추적하지 않도록 설정하는데 사용되는 텍스트 파일
- 프로젝트에 따라 공유하지 않아야 하는 것들이 존재하기 때문
- ex) venv, .venv
- 이미 Git의 관리를 받은 이력이 있는 파일이나 디렉토리는 적용 X

---

## Revert & Reset

### git revert <commit id>

- 특정 commit을 없었던 일로 만드는 작업
- 기존의 commit을 없었던 일로 처리 후 새로운 commit으로 추가
- :wq : vim 편집(메모창) 종료
- 변경사항을 안전하게 실행 취소할 수 있도록 도와주는 순방향 실행 취소 작업
- 기록이 손실되는 것을 방지
- 기록의 무결성과 협업의 신뢰성 향상

## git reset [옵션] <commit id>

- <commit id>까지 되돌아가기
- 되돌리기
- 특정 commit으로 되돌아 갔을 때, 되돌아간 commit 이후의 commit은 모두 삭제
- 삭제되는 commit 들의 기록을 어떤 영역에 남겨둘 것인지 옵션 조정 가능
- 코드 충돌 가능성 → remote에 올라간 commit은 절대 reset  X → revert O

- —soft : 삭제된 commit의 기록을 staging  area에 남김
- —mixed : 삭제된 commit들의 기록을 working directory에 남김 → 기본값
- —hard : 삭제된 commit들의 기록 X

---

### git rm —cached

- Git이 파악하고 있는 파일을  Git에서 제거
- Staging area에서만 파일을 제거 → add 했던 내역이 취소 및 파일은 유지
- commit이 없더라도 동

---

git restore —staged

- staging area이 추가된 변경 사항을 현재 버전으로 되돌리기
- add 했던 내역은 취소, 변경 사항은 유지
- 마지막 버전이 있어야 함 →  commit이 하나라도 존재

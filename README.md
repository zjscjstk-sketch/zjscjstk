🔎 git branch
브랜치를 생성하거나 목록을 확인하는 명령어임
브랜치 목록 확인

git branch
브랜치 생성

git branch feature/ui
브랜치 전환

git switch -c feature/ui
‼️ 새로운 기능을 개발할 때는 별도의 브랜치를 생성한 후 작업하는 것이 일반적임

1.2 브랜치 관리 전략
프로젝트마다 브랜치를 관리하는 규칙을 브랜치 전략(Branch Strategy)이라고 함
Git Flow는 대표적인 브랜치 전략 중 하나임
브랜치	역할
main	배포 가능한 안정 버전
develop	개발 내용을 통합하고 테스트하는 브랜치
feature/*	새로운 기능 개발
release/*	배포 준비
hotfix/*	운영 중 발생한 긴급 오류 수정

2. 브랜치 병합
git merge

다른 브랜치의 변경 내용을 현재 브랜치에 반영하는 명령어임
# main 브랜치에서 실행
git merge feature/ui
✔️ feature/ui 브랜치에서 작업을 완료한 뒤 main 또는 develop 브랜치로 병합할 때 사용함

2.1 Merge 방식
1️⃣ Fast-forward Merge
브랜치가 직선 형태로 이어져 있을 때 수행됨
새로운 병합 커밋을 만들지 않고 브랜치 포인터만 앞으로 이동함

2.2 Merge conflict
같은 파일의 같은 부분을 서로 다르게 수정하면 충돌이 발생함
Git이 자동으로 병합할 수 없는 경우 사용자에게 충돌 해결을 요청함
해결 방법
충돌이 발생한 파일 확인
원하는 내용으로 직접 수정
수정한 파일을 git add
git commit으로 병합 완료
✔️ Git은 가능한 경우 자동으로 병합하며, Git이 자동으로 병합할 수 없는 경우에만 Merge Conflict가 발생함
2️⃣ 3-way Merge
서로 다른 브랜치에서 각각 커밋이 추가된 경우 수행됨
병합 커밋(Merge Commit)이 새롭게 생성됨

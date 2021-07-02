# Git
2021.05.13 3년동안 SVN만 쓰다가 Git쓰려니까 어려워서 정리해보는 깃!!!

### 기본
  - 서버에 있는거 받을때
    - git 위치에서 cmd로! cmd가 간지니까
    - `git fetch origin`
    - `git pull origin main`    
  - 내가 한거 올릴때
    - `git add *` 모든파일, 뒤에 파일명 적어도됨
      - sublime merge 써서 맨날 stage 눌렀는데...
    - `git commit -m"커밋메세지"`
      - 이것도 sublime merge 써서 맨날 커밋메세지 쓰고 커밋버튼 눌렀는데...
    - `git push origin main`    
  - sublime merge 쓰면 편함! ㅋㅋㅋㅋㅋ
  - origin : remote 저장소 이름, 변경가능  
  - main : branch 이름

### Commit message 변경하기
  - push까지 했을경우
    - vi 에디터 사용
    - `git rebase HEAD~1 -i`
    - 나오는 창에서 i 누르면 insert 모드로 변경됨
    - pick을 reword로 변경
    - esc 키 누르고 `:wq` 입력
    - commit message 수정
    - esc 키 누르고 `:wq` 입력
    - `git push --force` 강제로 푸쉬
      - 근데 강제푸쉬 하는거 안좋다고 들었음... ㅠㅠ

### 폴더 삭제하기
  - 로컬, git 둘다 삭제
  - `rm -rf 폴더명`
  - commit push

### Resolve
  - Git 입장에서 생각해야됨
  - ours는 내꺼가 아니라 master를 지칭
  - theirs가 내꺼 라고 생각하면 편함
  - 계속 ours 쓰다가 구글링해봄
  - 출처 : http://www.ohyecloudy.com/ddiary/2017/12/12/til-git-checkout-ours-or-theirs/




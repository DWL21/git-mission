# git-misson
### 미션0-codeanywhere 컨테이너 생성
  * codeanywhere.com 회원가입 후 new container -> python 선택하여 새 컨테이너를 만든다.
  * new ternimal을 눌러 새 터미널 창을 열 수 있다. codeanywhere에서 모든 프로젝트는 workspace 디렉터리 안에서 관리해야 한다.

### 미션1-혼자 github 사용하기
1. github에서 git-misson-닉네임 repository를 만든다.
2. local pc의 터미널에서 해당 repository를 clone하고 자기 닉네임으로 된 branch를 만든다.
```
git clone https://github.com/(닉네임)/git-mission
git checkout -b (닉네임)
```
3. 터미널에서 git config --global user.name과 user.email을 설정한다. 로그를 남기려고 설정한다. global 옵션을 포함하면 local pc에 처음 한번만 설정해놓으면 된다. 모르면 ‘git global config’를 구글에 검색해 방법을 찾는다.
```
git config --global user.name "닉네임"
git config --global user.email "이메일 주소"
```
4. 해당 branch에 README.md 파일을 만들고 본 미션파일의 내용 전체를 복사하여 commit하고 push한다. 이때 커밋메세지는 docs:로 시작한다.
```
git add .
// 상태확인: git status
git commit -m "docs: readme 작성"
git push origin (브랜치명)
```
5. github에서 자기 닉네임 branch를 main(master) branch로 pull request를 한 다음 approve한다.

### 미션2-협업할 때 github 사용하기
1. github에서 git-misson repository를 fork한 후 clone한다.
```
git clone https://github.com/(닉네임)/git-mission
```
2. origin repository에 자기 닉네임으로 된 branch를 만든다.
```
git checkout -b (닉네임)
```
3. people/ 디렉터리에 닉네임.md 제목의 파일을 만들고 자기소개를 작성한다. 아래에 미션1의 README.md 파일 링크도 복사한다. 역시 commit후 push하며 커밋메세지는 docs:로 시작한다.
```
git add .
git commit -m "docs: readme 작성"
git push origin (브랜치명)
```
4. github에서 upstream(dwl21) repository의 main(master) branch로 pr을 요청한다. 이때 pr제목은 “[닉네임] 미션2 완료”로 한다.
5. merge가 되면 upstream repository의 main branch를 local pc로 fetch하고 local pc의 main branch에 merge한다. 완료되면 push하여 github에서 확인한다.
```
// git remote add <저장소 단축이름> <repository 주소>
git remote add upstream https://github.com/DWL21/git-mission
git fetch upstream main
git checkout upstream/main
파일 업데이트 확인 후
git checkout main
git merge upstream/main
```

### Q&A
> 모르는 부분은 구글에서 키워드로 검색하여 찾아보면 대부분 해결할 수 있다.  
1. git push할 때 id/password를 매번 요구함
	* 터미널에 config credential.helper store 명령어를 입력하면 다음 아이디/비밀번호를 요구할 때 캐싱해준다.
	* 아이디는 github닉네임이다.
	* 비밀번호는 ‘github 토큰 발급’을 구글에서 검색해 방법을 찾은 후 해당 토큰을 사용한다.
2. 미션2의 merge, pr 단계에서 conflict 발생함
	* 충돌 내용을 확인하여 수정한 후 commit한다. 모르면 ‘git 충돌‘을 구글에 검색해 방법을 찾는다.
3. fetch와 pull의 차이점
	* fetch는 변경사항을 불러온다. (remote repository)/(브랜치 이름)으로 checkout하여 확인할 수 있다.
	* merge는 fetch된 변경사항을 local branch에 실제로 반영한다.
	* pull은 fetch와 merge를 동시에 하는 기능이다.
```
git checkout main
git pull <저장소 이름> main
```

4. 리눅스 터미널 명령어 사용법
```
ll: 현재 디렉터리 파일과 폴더 탐색
cd <디렉터리명>: 해당 디렉터리로 이동
cd ..: 상위 디렉터리로 이동
```
  * tip: 파일명, 디렉터리명은 일부만 입력하고 TAB 두번 누르면 자동완성이 된다.
  * 이외에는 ‘리눅스 터미널 명령어 사용법’을 구글에 검색해 방법을 찾는다.

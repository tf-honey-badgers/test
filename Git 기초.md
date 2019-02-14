# Git 기초

## 처음 설정하기
프로그램 설치 : SourceTree 다운로드 > BitBucket 회원가입 (실제 사용하지는 않는다) <br/>
local repo 만들기 : Clone > https://github.com/tf-honey-badgers/project01-message-board.git > local repo 저장 위치 지정 > "Clone" 클릭 <br/>
branch 가져오기 : SourceTree 중앙 창에서 "origin/development" 태그가 있는 줄을 더블클릭 > checkout new branch에서 이름을 "development"로 작성 > "OK" <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; >> remote repo의 development branch를 나의 local repo로 가져온다. <br/>
branch 만들기 : "New Branch" 창에 실제 내가 사용할 personal branch 명 입력 > "Create Branch" <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; >> 사실 3번째 branch는 개인용이라기보다는 특정 주제나 기능을 구현할 때 사용하고, 작업 완료 후에는 development branch로 merge한다. <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; >> remote repo에 branch 만들기 : local branch 만들고 remote repo에 push하면 remote repo에서도 만들어진다.

## GitHub에 코드 올리기
Add/Stage > Commit > Pull > Push <br/>
&nbsp;&nbsp;&nbsp; >> Add/Stage -> Git에서 트래킹하고 있지 않는 파일을 트래킹하게 한다. <br/>
&nbsp;&nbsp;&nbsp; >> Commit -> local repo에 저장하는 것. <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; >> Commit할 때는 메세지를 추가할 수 있는데 의미 있는 메세지를 추가할 것 <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "올라가라" 같은 것은 사용하지 말고 차라리 "테스트"라고 쓸 것 <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "로그인 코드 수정" 등을 사용할 것 <br/>
&nbsp;&nbsp;&nbsp; >> Pull 후 Push -> remote repo에서의 코드가 변경되었을 가능성이 있기에 항상 먼저 가져온 후 내 코드를 올린다. <br/>

## 용어 정리
01. remote repository -> GitHub 본사 서버, 실제로 github.com에 접속하면 볼 수 있는 코드, 팀원이 볼려면 여기서 pull한다.
02. local repository -> 본인 컴퓨터에 위치, 본인만 볼 수 있다.
03. "master" branch -> default branch, 즉시 배포 가능한 완전한 코드만 올림, 사용하지 말 것. <br/>
04. "development" branch -> 실제로 개발할 때 사용할 branch, 팀의 코드를 합치는 곳. <br/>
05. 개인 branch -> 각 팀원이 사용할 개인 branch, 대부분의 코드는 여기로만 올릴 것. <br/>
06. "origin" -> remote repo <br/>
07. "origin/master" -> remote repo에 있는 master branch (즉, root branch) <br/>
08. "master" -> local repo의 master branch <br/>
09. "origin/HEAD" -> 기본적으로 HEAD는 가장 최신 commit(즉, 가장 최신 버전)를 가리킴. <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; >> (추정) origin/HEAD는 origin의 가장 최신 commit을 가리키며 clone했을 때 얻을 버전을 가리킨다. <br/>
10. "origin/development" -> remote repo의 development branch <br/>
11. "development" -> local repo의 development branch <br/>

## 기타
&nbsp;&nbsp; >> Branch간 이동하면 해당 branch에 있어야할 파일 등이 자동으로 바뀐다. 파일탐색기에서도 바뀌는 것을 볼 수가 있다. 최근 branch를 변경했다면 지금이 어느 branch인지 SourceTree에서 확인하고 작업할 것! <br/>
&nbsp;&nbsp; >> Branch merge는 두 개 branch를 하나로 합치는 것이 아니다! destination branch로부터 target branch로 destination branch의 모든 내용을 복붙하는 것이다. 실제로 destination branch는 살아있으며 destination branch에서 수정을 한다고 해도 target branch에 merge한 내용은 수정되지 않는다 (또다시 merge하지 않는 이상) <br/>
&nbsp;&nbsp; >> 같은 파일의 같은 줄을 다르게 수정한 상황에서 merge 시 충돌난다 -> 내가 판단하여 직접 수정하거나 지시를 내려야 함. <br/>
ex) 출처 : git-scm.com <br/>
"<<<<<<< HEAD:index.html" <br/>
"<div id='footer'>contact : email.support@github.com</div>" <br/>
"=======" <br/>
"<div id='footer'>please contact us at support@github.com</div>" <br/>
">>>>>>> iss53:index.html" <br/> <br/>
&nbsp;&nbsp;&nbsp;&nbsp; master branch, iss53 branch에서 같은 이름의 index.html 파일의 같은 줄을 다르게 작성했다. git은 자동 merge하지 않고 일시중단하여 사용자의 수동 작업을 요구한다. <br/>
&nbsp;&nbsp; >> SourceTree에서 branch만 만들면 graph에 나타나지 않는다. 그 이유는 branch를 만들어도 그 이전 branch(들)에 실제로 달라진 것은 없기 때문이다. 기존 branch에서 새롭게 commit을 해야지 graph선이 분리된다.

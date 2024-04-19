

1분 : 프로젝트 소개

* 팀 소개 : [3합] 이행도, 류원형, 홍진권, 김보현
* 팀 이름 뜻 : 3조의 ‘3’을 본 떠서 찰떡인 이름이 없을까 고민하다가, 첫 프로젝트인만큼 잘 어우러져 프로젝트를 수행하고자 3합으로 팀 이름 결정
* 피그마 구성 : 3조 NOTION 참고

2분 : 미니 프로젝트 시연 영상

* 영상 시청하며 구현한 기능들에 대한 간단 설명 :
1. 홈페이지를 처음 오픈하면, 상단 배너와 중앙 팀 로고만 보일 수 있도록 배치
	로고 클릭 시 맴버 소개 카드와 방명록을 작성할 수 있는 요소 확인 가능

2. 맴버 이미지 클릭 시 개인 상세 페이지로 진입, 상세 페이지마다 각자 조원이 원하는 음악 삽입
	싸이월드처럼 각자의 공간에 각저의 색깔을 더할 수 있는 방법을 고민하다 bgm을 넣어보자기로 협의,
	상세페이지 하단 이미지를 보면 자유롭게 사이즈도 맞추지 않고 배치, 이 것도 각 조원마다 원하는 형태로 넣어 자유롭게 제작해 보는 것으로 논의 진행 

3. 방명록 기능
	이 프로젝트 주제는 ‘조원을 소개하는 홈페이지’ 를 제작, ‘홈페이지에 방문하는 사람들이 실시간으로 피드백을 남길 수 있으면 좋겠다’ 판단하여 팀원 간 논의 후 방명록 제작 진행
	글을 쓰면 실시간으로 업로드 되는 기능
	실시간으로 글을 작성하는, 예시로 블로그나 유튜브의 댓글, 식당 리뷰들도 모두 수정 삭제 기능을 제공하기에 함께 서비스 내 포함시켜 보았고, 홈페이지 내 기능적으로 불필요하다 판단 회원가입, 로그인 기능을 구현하지 않아서
	방명록 작성 시 패스워드를 함께 입력하여 작성자만 수정, 삭제할 수 있도록 구성




3분 30초 : 프로젝트 진행과정 소개

* 프로젝트를 진행하며 어려웠던 부분 :
    * 팀원들간 회의한 방향대로 홈페이지를 처음부터, 새롭게 제작한다는 것이 다소 막막하여 강의를 재수강하며 복습 병행
 		욕심은 많으나, 모두 개발이 처음인 3조가 겪었던 가장 큰 딜레마는 깔끔한 디자인, 역동적이고 다양한 기능을 보유한 사이트를 만들고 싶었으나 한계가 크다는 점

* 프로젝트 진행 전 약속한 우리들의 목표 :
    * 목적을 설정한 후 구현할 기능을 설정하는 것
    * 단순히 코드를 따라쳐 보는 것이 아닌, 이해하며 작성해 보는 것
    * 작성한 코드가 나중에 보면 말이 안되더라도 어떻게든, 반드시 구현해보는 것 

* 코드를 작성하며 마주한 문제들과 해결방식
    * 방명록을 제작하며 마주한 어려움과 해결방법 (방명록 기능을 다음과 같이 구현하고 싶었던 이유 / 마주한 문제 / 해결방식)


    * 로고의 움직임을 준 방식에 대해 (다음과 같이 구현하고 싶었던 이유 / 마주한 문제 / 해결방식)

		팀원들과 협의하며 깔끔한 홈페이지로 첫인상을 주기를 원하여 많은 요소들을 hide처리 후 토굴 방식으로 오픈 할 수 있도록 설정 하였으나,
		깔끔함을 넘어 허전해 보이기 시작
 
		'로고를 직접 만들었으니, 해당 로고가 맨 처음 가운데에 크게 배치되어 있으면 우리가 처음 원하는 느낌을 줄 수 있겠다!’ 판단
		가운데 로고를 클릭하면, '맴버소개', '방명록' 요소들이 부드럽게 등장, 로고의 크기가 작아지며 위로 올라갈 수 있도록 구현’ 하는 것을 목표로 진행

		처음 더 깔끔하게, 잘 디자인하는 것이 중요하다 생각하여 2번 방법으로 진행하려 했으나 막혔던 부분이
		‘버튼 클릭 시 이동하려면 로고 하나에 두 개의 class를 만들어 클릭 전과 클릭 후를 나누어 디자인이나 움직임을 줘야 하는 건가?’
		‘로고가 움직이면서 동시에 다른 요소들이 등장해야 하는데 ..’
		 	 
		미니 프로젝트 시작 전 팀원들고 함께 설정한 목표처럼
		작성한 코드가 나중에 보면 말이 안되더라도 어떻게든 구현해보는 것
 
		그래서 다음과 같은 방식으로 작성

		//홈페이지가 오픈되자마자 맴버카드, 방명록의 여러 요소들을 숨기기 처리
	$(document).ready(function () {
            $('#memberbox').hide();
            $('#speech-bubble').hide();
            $('#t1').hide();
            $('#list').hide();
            $('#button').hide();
        })
        
//가장 위에 있는 로고를 클릭하면 맴버카드, 방명록 뿐만 아니라 두 개의 버튼이 모두 토글될 수 있도록 설정
        $("#topbtn").click(async function () {
            $('#memberbox').toggle();
            $('#speech-bubble').toggle();
            $('#t1').toggle();
            $('#list').toggle();
            $('#center-button').toggle();
            $('#button').toggle();
        })

//중간에 위치하고 있는 로고를 클릭하면 맴버카드, 방명록 뿐만 아니라 두 개의 버튼이 모두 토글될 수 있도록 설정
        $("#centerbtn").click(async function () {
            $('#memberbox').toggle();
            $('#speech-bubble').toggle();
            $('#t1').toggle();
            $('#list').toggle();
            $('#center-button').toggle();
            $('#button').toggle();
        })
￼

* 여러 요소들을 가로로 원하는 방식으로 정렬하는 것

가로로 정렬하는 것은 말로만 듣거나 강의를 수강하면서 여러 부분 참고할만한 것들이 있어 다소 쉬워보였으나 생각보다 애를 먹은 부분

다음과 같은 문제점들이 발생하였는데,

1. 이미 가로로 정렬된 부트스트랩 내 하나의 요소를 그대로 가져와 활용했을 때와 달리 가로로 정렬이 되지 않았다는 점
2. 어찌어찌 요소들을 가로 정렬해보았으나, 문구가 밖으로 삐져나가거나 배치가 제멋대로 되는 현상이 발생

display: flex 기능을 활용 문제점을 해결

<div class="box"> // 사진과 글을 감싸고 있는 BOX
<div class="photo"> <img src="이미지 url"> </div> // 조원 사진
<div class="intro"> // 조원의 정보를 담은 글
<h2><span style="color: #ffd400;">이름</span> : 이름</h2> 
<br>
<h2><span style="color: #ffd400;">나이</span> : 나이</h2>
<br>
<h2 button class="my-underline" onclick="window.open('')"></button>블로그 링크이동 버튼</h2>
<h2 button class="my-underline" onclick="window.open('https://www.instagram.com/jinkwonhong/')">
</button>인스타그램 링크이동 버튼</h2>
<br>
<h2><span style="color: #ffd400;">TMI</span> : 내용 1</h2>
<br>
<h2>내용 2-1</h2>
<h2>내용 2-2</h2>
<br>
<h2>내용 3-1</h2>
<h2>내용 3-2</h2>
</div>
</div>

맴버 사진과 맴버의 이름, 나이, TMI 등 여러가지 정보를 가로 형태로 배치하기 위해 다음과 같이 HTML 부분을 작성
box로 사진과 글을 감싸고,
내용들은 <br>로 문단을 나누어 여러 줄로 깔끔하게 정리되어 보여질 수 있도록 설정

.box {
display: flex;
justify-content: center;
}
 
.photo {
margin: 20px;
}
 
.intro {
margin: 20px;
color: white;
}

위와 같이 CSS를 작성하여 부모 구역(box)을 display: flex로 가로로 배치,
사진과 글 간 간격을 주기 위해 margin 기능을 활용하여 결과적으로 원하는대로 배치

* 여러 요소들을 가로로 원하는 방식으로 정렬하는 것

1. document를 활용해서 방명록 구현

document.getElementById("id"); // 요소 한 개 
document.getElementsByTagName("태그명"); // 배열 반환

요소.속성 = 값 == 요소.setAttribute("속성명", "값");
alert(요소, 속성); == 요소.getAttribute("속성명");
요소.setAttribute("속성명", "값");

document.createElement("태그명");
부모요소.appendChild("새요소");
부모요소.removeChild(삭제요소);

2. function과 document, createElement를 활용해서 새 div를 생성하고 id, cnt를 1씩 더하게 해서 순서를 지정
   수정과 삭제 버튼은 onclick으로 클릭 됐을 때 작동되게 구현, 이와 동일하게 수정과 삭제에서 글번호를 입력해서 활용
		
function mkDiv(writer, pwd, content) {
		let newDiv = document.createElement("div");//새 div태그 생성  <div id="d_1" pwd='111'>
		newDiv.id = "d_" + cnt;//생성한 div에 id 지정. d_cnt
		newDiv.pwd = pwd;
		let html = ""; //생성된 div에 출력될 내용
		html += "writer:<span id='w_"+cnt+"'>" + writer + "</span><br/>";
		html += "content:<span id='c_"+cnt+"'>" + content + "</span><br/>";
		html += "<input type='button' value='수정' onclick=editForm(" + cnt
				+ ")>"; //editForm(2)
		html += "<input type='button' value='삭제' onclick=del(" + cnt + ")>";
		newDiv.innerHTML = html;
		cnt++;
		return newDiv;

	function editForm(cnt) {
		let editDiv = document.getElementById("d_" + cnt); //수정할 글의 div
		let editForm = document.getElementById("editf");
		editDiv.appendChild(editForm);
		let writer = document.getElementById("w_" + cnt).innerHTML;
		let content = document.getElementById("c_" + cnt).innerHTML;
		document.getElementById("editwriter").value = writer;
		document.getElementById("editcontent").value = content;
		document.getElementById("editbtn").cnt = cnt;//버튼에 cnt속성을 추가해서, 수정 글번호를 저장
		editForm.style.display = '';

  3.취소키 구현

  function cancel() {
		let editForm = document.getElementById("editf");
		editForm.style.display = 'none';
		document.getElementsByTagName("body")[0].appendChild(editForm);

4.편집 및 삭제 키 구현

if, else를 활용해서 상황을 나눴고 alert를 추가해서 상황 알림

function edit() {
		let cnt = document.getElementById("editbtn").cnt;
		let editDiv = document.getElementById("d_" + cnt);
		let pwd2 = document.getElementById("editpwd").value;//수정폼에 입력한 글 비밀번호
		if (editDiv.pwd != pwd2) {
			alert("비밀번호 불일치. 수정불가");
		} else {
			let newWriter = document.getElementById("editwriter").value;
			let newContent = document.getElementById("editcontent").value;
			document.getElementById("w_" + cnt).innerHTML = newWriter;
			document.getElementById("c_" + cnt).innerHTML = newContent;
            alert("수정 완료")
		}
		document.getElementById("editwriter").value = "";
		document.getElementById("editcontent").value = "";
		document.getElementById("editpwd").value = "";
		cancel();
	}
	function del(cnt) {
		let pwd = prompt("글 비밀번호");
		let delDiv = document.getElementById("d_" + cnt);
		if (pwd == delDiv.pwd) {
			document.getElementById("list").removeChild(delDiv);
            alert("삭제완료")
		}else{
			alert("비밀번호 불일치. 삭제취소");
		}
	}

# [이론] HTML : Form 요소 🙋🏻‍♂️ 
### 💡 이론 내용
- HTML의 개발자가 알아야할 Form 요소에 대해서 알아 보자.

### 웹 폼
로그인, 회원 가입, 주문 정보 등을 처리하기 위해서는 사용자로 부터 필요한 데이터를 입력 받아야 한다.

<pre  id="aa3c209b-4835-48c9-bc7f-8b604eec96ed" class="code"><code>&lt;!DOCTYPE html&gt;

	&lt;html lang=&quot;en&quot;&gt;

		&lt;head&gt;
			
			&lt;meta charset=&quot;UTF-8&quot;&gt;

			&lt;meta http-equiv=&quot;X-UA-Compatible&quot; content=&quot;IE=edge&quot;&gt;

			&lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot;&gt;

			&lt;title&gt;Document&lt;/title&gt;

		&lt;/head&gt;

&lt;body&gt;
	
	&lt;!--form 태그 알아 보기--&gt;

	&lt;form action=&quot;http://localhost/login.php&quot;&gt;

	&lt;!--사용자가 입력한 정보들을 어디로 보낼것 인가 하는 정보는 action에 작성한다--&gt;
	
		&lt;p&gt;아이디 : &lt;input type=&quot;text&quot; name=&quot;id&quot;&gt;&lt;/p&gt;

		&lt;p&gt;비밀번호 : &lt;input type=&quot;password&quot; name=&quot;pwd&quot;&gt;&lt;/p&gt;

		&lt;p&gt;주소 : &lt;input type=&quot;text&quot; name=&quot;address&quot;&gt;&lt;/p&gt;

		&lt;p&gt;주소 : &lt;input type=&quot;number&quot; name=&quot;number&quot;&gt;&lt;/p&gt;

		&lt;input type=&quot;submit&quot;&gt;

	&lt;/form&gt;
&lt;/body&gt;

&lt;/html&gt;</code></pre>

어떤 회원 가입을 위해 필요한 다양한 정보를 입력 받기 위한 것으로 `form 요소` 안에 `input, textarea, select ,button, fieldset, label `들의 다양한 요소가 포함 됨을 알 수 있다. 여기서는 기존부터 사용 되어 왔던 이러한 요소들을 비롯하여 , HTML5 에서 새롭게 추가된`datalist 요소`와 `output 요소`도 사용 가능 하다.

### form 요소</h3>
 웹페이지에서 사용자로부터 입력을 받아 서버로 전달하기 위한 입력 양식을 웹 폼 (form, 간단히 폼) 이라고 하며, 웹 폼 안에서 사용 되는 다양한 요소들을 폼 요소(fom element)라고 한다.

웹 폼은 `input, textarea, select , datalist , output`등의 폼 요소를 사용 하여 다양한 형태의 사용자 입력을 받기 위한 컨테이너 역할을 수행하며, 그 자체로는 화면에 아무것도 나타나지 않는다.

- form 요소는 아래와 같은 속성이 사용 된다.
###
💡form 요소의 속성
--- 
|속성	                               |설명                          |
|--------------------------------------|-----------------------------|
|action = "URL"         |폼이 제출될 때 폼 데이터를 전달받아 처리할 페이지의 주소를 지정           |
|method="전송방식"           |폼 데이터를 제출할 때 사용 하는 HTTP 방법 : `값 → GET , POST`            |
|name="이름"|폼의 이름을 지정|
|accept-charset="인코딩"        |폼 제출을 위해 사용 되는 문자 인코딩 방식을 지정          |
|autocomplete=" on / off "        |폼의 `input 요소`에서 자동 완성 (autocomplete) 기능의 사용 여부를 지정           |
|enctype="인코딩"|`"method=post"` 인 경우 서버로 제출 될 때 폼 데이터의 인코딩 방식을 지정
|novalidate        |제출 시 폼 데이터의 유효성을 검사하지 않도록 지정           |
|target="창"         |폼 제출 후에 서버로 부터 전달 받은 처리 결과를 보여 줄 창을 지정: `값 → _blank, _self(기본값), _parent, _top, 프레임 명`            |


### 
💡method 속성의  전송 방식의 비교
---
|                |method="GET"                 |method = "POST"                |
|----------------|-------------------------------|-----------------------------|
|전송 형태|기본값, 폼 데이터가 이름과 값의 쌍 형태로 URL에 포함되어 전송            |HTTP Request 헤더 속에 포함시켜 전송 |
|데이터 길이    |최대 2048 글자         |제약이 없음          |
|보안      |`"URL?name=value&name=value"` 와 같이 전송되어 내용의 확인이 가능 → 보안이 중요하지 않은 데이터(예: 검색어 등) 전달에 많이 사용 → `'이전페이지' 버튼`을 통한 이동이 가능|보안이 필요한 로그인 정보, 회원 정보 등 개인 정보 전송에 많이 사용 → `'이전페이지' 버튼`을 누르면 데이터를 다시 보내야 한다는 `경고`가 표시|


#### ✏️알게된 부분
- 벡엔드 개발자가 꼭 알아야 하는 HTML 요소중에 한 부분이다.
- form 요소에서 전송 방식이 2가지가 있다.
	#### 내일 운명은 오늘 만들어 지는 거다.	 

#### 🙋🏻‍♂️참고문서
- HTML5


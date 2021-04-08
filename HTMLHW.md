# HTML 과제
> HTML 주석 달기
```html
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="utf-8">
<meta name="description" content="HTML태그 샘플 페이지1입니다.">
<title>HTML샘플1</title>
<style type="text/css">
</style>
</head>
<body>
<div>
<header>
<h1>상단 헤더 영역</h1>
</header>
<div>
<h2>좌측 메뉴 영역</h2>
<ul>
<li><a href="[<http://www.mixedcode.com>](<http://www.mixedcode.com/>)" target="_blank">믹스드코드닷컴</a></li>
<li><a href="[<http://www.naver.com>](<http://www.naver.com/>)" target="_blank">네이버</a></li>
<li><a href="[<http://www.daum.net>](<http://www.daum.net/>)" target="_blank">다음</a></li>
</ul>
</div>
<div>
<section>
<h2>본문</h2>
<p>
첫번째 단락 본문글입니다.
</p>
<p>
첫번째 단락 본문글입니다.
</p>
<br />
</section>
</div>
<footer>
<p>바닥글</p>
</footer>
</div>
<script type="text/javascript">
</script>
</body>
</html>
```
---
```html
<!DOCTYPE html>
<html lang="ko"> // 한글 사용

<head>
    <meta charset="utf-8">// 모든 언어 사용 가능
    <meta name="description" content="HTML태그 샘플 페이지1입니다.">
    <title>HTML샘플1</title> 페이창 이름
    
    <style type="text/css">  </style> // CSS 

</head>

<body>
    <container>
        <header>
            <h1>상단 헤더 영역</h1>
        </header>  <!--상단해드--> 
        <div>
            <h2>좌측 메뉴 영역</h2>
            <ul>
                <li><a href="[<http://www.mixedcode.com>](<http://www.mixedcode.com/>)" target="_blank">믹스드코드닷컴</a></li>
                <!--li태그 리스트 믹스드코드닷컴을 누르면 다른 창에 나타나게 해라-->
                <li><a href="[<http://www.naver.com>](<http://www.naver.com/>)" target="_blank">네이버</a></li>
                <!--li태그 리스트 네이버을 누르면 다른 창에 나타나게 해라-->
                <li><a href="[<http://www.daum.net>](<http://www.daum.net/>)" target="_blank">다음</a></li>
                <!--li태그 리스트 다음을 누르면 다른 창에 나타나게 해라-->
            </ul>
        </div>

        <div>
            <section><!--구획 나눔-->
                <h2>본문</h2> <!--글차 크기-->
                <p><!-- 하나 문단 사용-->
                    첫번째 단락 본문글입니다.
                </p>
                <p>
                    첫번째 단락 본문글입니다.
                </p>
                <br /><!--줄바꿈-->
            </section>
        </div>
        <footer> <!--풋터 부분-->
            <p>바닥글</p>
        </footer>
    </container>
    <script type="text/javascript"> </script> <!--자바 스크립트 구문 사용 하는 부분-->
</body>

</html>

```

> 주석 달기 연습 

[Back to Contents](../README.md)
# Frontend Interview QnA
Frontend 면접 질문과 답

### HTML 관련 질문
* doctype이 무엇을 하는 것인가요?
  * 문서의 종류를 선언하는 태그
  * HTML, XHTML, HTML5 어떤걸로 마크업 할지 정해야 함.
  * 마크업 문서의 요소와 속성등을 처리하는 기준이 되며 유효성 검사에 이용됨.
  * MIME(Multipart Internet Mail Extensions)
    * 콘텐츠 타입, Head 요소에 있음.
    * 다음 세가지 콘텐츠 타입 중 하나로 송신됨.
    * text/html : 브라우저가 문서를 HTML로 렌더링
    * application/xhtml+xml : XHTML을 이 타입으로 송신하게 되면 IE7 이하 버전은 페이지를 표시 못함
    * XML
* 표준모드(standards mode)와 쿽스모드(quirks mode)의 다른 점은 무엇인가요?
  * DTD를 보고 최신문서면 표준모드, 오래된 문서면 쿽스모드로 렌더링
  * 표준모드
    * 
* XML과 XHTML의 다른 점은 무엇인가요
* XHTML을 이용한 페이지의 한계점은 무엇이 있나요?
* application/xhtml+xml으로 지정한 페이지에 어떠한 문제가 있나요?
* 다국어가 포함된 페이지는 어떤 방식으로 제공하나요?
* 다국어 페이지를 제공하는 여러 방법에 관해 설명해주세요.
* data-속성은 무엇을 하는 것인가요? 사용했을 때 이점은 무엇인가요?
* HTML5를 오픈 웹 플랫폼(open web platform)으로 생각해본다면, 어떤 것들로 구성돼 있을까요?
* 쿠키(Cookies)와 세션저장소(sessionStorage)와 로컬저장소(localStorage)의 차이점을 설명해주세요.
* <script>, <script async>와 <script defer>의 차이점에 관해 설명해주세요.
* CSS<link>를 <head></head>사이에 쓰는 것과 JS<script>를 <body></body>뒤에 사용하는 것은 좋은 사용법일까요? 어디에 배치하는 게 좋을까요?
* Progressive rendering이란 무엇인가요?
* 이미지 태그에 srcset 속성을 사용하는 이유는 무엇인가요? 브라우저가 이 속성을 가진 콘텐츠를 평가할 때 사용하는 과정을 설명해보세요.
* HTML templating language를 사용해 본 경험이 있나요?

# MyJavaNote

[까먹기 쉬운거(오류, 기본 설정)]

tomcat 실행 오류(startup.bat http://localhost:8080)
- 이미 tomcat이 실행 중인지 확인(자바 프로젝트, bat파일)
- JAVA_HOME의 경로가 jdk가 있는 경로인지 확인(C:\Program Files\Java\jdk-17)

프로젝트명 우클릭 - Properties - Web Projet Settings - Context root > "/"로 변경
- 프로젝트 경로를 Context가 아닌 ROOT로 사용하기 위함
- 기본값을 가상경에서 root로 바꿈

브라우저의 해석방식
html > 태그를 인식하여 반영함 - 엣지
txt > 태그 그대로 출력함 - 크롬
- 서버에서 인코딩(UTF-8)과 해석방식(text/html; charset=UTF-8)을 알려줘야함
- CharaterEncoding/ContentType (filter)

WAS 기본 인코더 ISO-8859-1를
UTF-8 로 간접 변경
1 바이트 해석 > 2 바이트 해석 변경
영어 1byte, 한글 2byte

[사전 지식]
1. 프로그래밍 과정
코드 작성(.txt > .java 파일 생성) - 컴파일(cmd > javac > .class) - 배포(classes > .class, mapping > .xml) - 서버 on(startup.bat-winOS) - 브라우저 요청(localhost:8080/~ 입력)

클라이언트가 문서 요청 시 네트워크를 통해 서버에서 문서를 만들어 보냄(1 과정 진행)
자동화 이전에 직접 문서를 수정함 > 수정 할 때마다 다시 다운받음 > 1 과정반복(했던 일 또 해) > 자동화된 IDE, framework 사용(딸깍 on)

브라우저 - server - WAS - (중간과정) - Servlet

중간과정 > filter1,2, servlet2,3 등등




[사이트를 만들기 위해 필요한 것]

데이터 전송 과정
html <form> - servlet

입력(UI) - html, jsp

html에서 데이터를 보내줄 때 받는 입장에선 출처를 알아야하기때문에 폼 태그를 정의하고
<input name="x" value="3"> 이런 식으로 전달함
자바에서 request.getParameter("name")으로 name을 확인하고 value값을 객체에 저장함.(자바에서 알아서 생성된 객체임)



연결 - tomcat 얘(통칭 WAS 웹서버) 쓰면 알아서 해줌. 구동원리만 알면 됨
브라우저에서 페이지를 요청하면 그게 맞는지 확인하고 응답해줌
class파일만 있으면 됨 나머진 매핑으로 요처받음(/hello)

localhost = ipconfig IPv4(여러 기기에서 접속가능)

servlet(let = 조각, ServerApplicationLet > 여러 문서중 하나만 제공되는 문서 = 현재 실행 중인 html 페이지)

context - webapps\root 폴더에서만 다루기 어려워, 나눠서 따로 개발하고 싶을 때 가상 경로만들어 개발함 webapps\contextFile (xml > META-INFO 권장)
root파일에 없지만 root파일에 있는것처럼 씀

계산 - java

요청과 응답으로 나눔
요청: 브라우저(크롬) > 서버(톰캣)
응답: 서버 > 브라우저

HttpServlet의 시스템을 가져와 빌려 씀(Http는 하나의 연락수단)
service()에서 구현함(보안상 Http > Https)


데이터 저장 - ArrayList, DBMS
DB 연동 대신 ArrayList 사용 가능(학습용)



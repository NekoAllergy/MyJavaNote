# MyJavaNote

[까먹기 쉬운거(오류)]

tomcat 실행 오류(startup.bat http://localhost:8080)
- 이미 tomcat이 실행 중인지 확인(자바 프로젝트, bat파일)
- JAVA_HOME의 경로가 jdk가 있는 경로인지 확인(C:\Program Files\Java\jdk-17)

프로젝트명 우클릭 - Properties - Web Projet Settings - Context root > "/"로 변경
- 프로젝트 경로를 Context가 아닌 루트로 사용하기 위함


[사전 지식]
1. 프로그래밍 과정
코드 작성(.txt > .java 파일 생성) - 컴파일(cmd > javac > .class) - 배포(classes > .class, mapping > .xml) - 서버 on(startup.bat-winOS) - 브라우저 요청(localhost:8080/~ 입력)

클라이언트가 문서 요청 시 네트워크를 통해 서버에서 문서를 만들어 보냄(1 과정 진행)
자동화 이전에 직접 문서를 수정함 > 수정 할 때마다 다시 다운받음 > 1 과정반복(했던 일 또 해) > 자동화된 IDE, framework 사용(딸깍 on)





[사이트를 만들기 위해 필요한 것]

입력(UI) - html, jsp
JSP 구현은 한번만 함.
이후 따로 툴 써서 해결

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



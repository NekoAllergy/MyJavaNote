# MyJavaNote

까먹기 쉬운거(오류)
tomcat 실행 오류(startup.bat http://localhost:8080)
- 이미 tomcat이 실행 중인지 확인(자바 프로젝트, bat파일)
- JAVA_HOME의 경로가 jdk가 있는 경로인지 확인(C:\Program Files\Java\jdk-17)

사전 지식

1. 프로그래밍 과정
코드 작성(.txt > .java 파일 생성) - 컴파일(cmd > .class) - 배포(classes > class, xml) - 서버 on(startup.bat-winOS) - 브라우저 요청(localhost:8080/~ 입력)

클라이언트가 문서 요청 시 네트워크를 통해 서버에서 문서를 만들어 보냄(1 과정 진행)
자동화 이전에 직접 문서를 수정함 > 수정 할 때마다 다시 다운받음 > 1 과정반복(했던 일 또 해) > 자동화된 IDE, framework 사용(딸깍 on)





사이트를 만들기 위해 필요한것

입력(UI) - html, jsp
자바로 페이지 구현은 한번만 함.
이후 따로 툴 써서 해결

연결 - tomcat 얘(통칭 WAS 웹서버) 쓰면 알아서 해줌. 구동원리만 알면 됨
요청에 따른 페이지를 응답해줌
class파일만 있으면 됨 나머진 매핑으로 요처받음(/hello)

localhost = ipconfig IPv4

servlet(let = 조각, ServerApplicationLet > 여러 문서중 하나만 제공되는 문서 = 현재 실행 중인 페이지)
HttpServlet 시스템을 가져와 빌려 씀(Http는 하나의 연락수단)

context - webapps\root 폴더에서 나눠서 따로 개발하고 싶을 때 가상 경로만들어 개발함 webapps\contextFile (xml > META-INFO 권장)

계산 - java

요청과 응답으로 나눔
요청: 브라우저(크롬) > 서버(톰캣)
응답: 서버 > 브라우저

service()에서 구현함


데이터 저장 - arraylist, DBMS
DB연동 대신 ArrayList 사용 가능(학습용)



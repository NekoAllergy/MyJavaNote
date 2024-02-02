# MyJavaNote
도움 ChatGPT-4

[까먹기 쉬운거(오류, 기본 설정)]

선언은 단 한번, 연산은 반복.

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

== 동일한 객체를 참조하는지(=**해시코드**가 동일한지 instance@**15db9742**)

instance.equals() 객체가 가진 값이 동일한지

[가끔 고착화된 구린 번역 중 집고 넘어가는 점]
객체와 인스턴스의 차이
객체는 아직 구체화되지않은 이론에 가까움(설계는 되어있음)
인스턴스는 구체화된 객체(프로그램 실행 시 실제 메모리상에 올라감)

class ObjectA를 만듬 > 객체임(인스턴스는 아님)
(메서드랑 전역번수가 있음)
private int EE;
method(){};

main()에 그 클래스의 이름을 instanceA로 함 > 인스턴스임(근데 규칙에 따르면 객체도 맞음)
ObjectA instanceA(이게 인스턴스) = new ObjectA();

instanceA.method()로 사용가능.

다른 설명으론 인스턴스는 사례라고 함.
instanceA, instanceB 등등 여러 이름의 인스턴스 생성가능 어차피 같은 클래스에서 나온거라 기능은 같음

부모 자식 > super sub
상속 개념을 다룰 때 부모 자식은 parents child를 그대로 갖다쓴거
이후 super sub로 바뀜



[사전 지식]
1. 프로그래밍 과정
코드 작성(.txt > .java 파일 생성) - 컴파일(cmd > javac > .class) - 배포(classes > .class, mapping > .xml) - 서버 on(startup.bat-winOS) - 브라우저 요청(localhost:8080/~ 입력)

클라이언트가 문서 요청 시 네트워크를 통해 서버에서 문서를 만들어 보냄(1 과정 진행)
자동화 이전에 직접 문서를 수정함 > 수정 할 때마다 다시 다운받음 > 1 과정반복(했던 일 또 해) > 자동화된 IDE, framework 사용(딸깍 on)

Html은 그냥 아무런 기능 없는 전자 문서라고 생각하면 된다.
<> 이런 태그를 사용해서 넣고싶은 추가 기능을 입맛대로 넣는 것이 html.
태그는 곧 기능 그 자체이고 기능에는 속성을 가진다.
이 속성은 기능을 좀 더 디테일하게 작동하도록 만들어준다.

데이터의 요청 응답 과정
브라우저 - server - WAS - (중간과정) - Servlet

중간과정 > filter1,2, servlet2,3 등등

MVC 모델
프로젝트의 구조를 정하는 방법
미리 파일을 역할 별로 나눠서 코드 작성을 용이하게 함.

Controller
브라우저에서 요청을 받아 모델과 뷰에 적용한다.
데이터의 처리가 이루어진다. 중간에 끼인 데이터 유통업자

Model
(주로) DB의 데이터가 정해진 규칙에 따라 전달됨.
내가 어떤 데이터를 어떻게 쓸건지 정하는 곳

View
웹 디자인을 담당하는 부분
얼굴마담

XML JSON - 데이터를 설정하는 파일 확장자
XML = 틀(엄격함,입맛대로)
JSON = MZ(가벼움,간결)

RestAPI
이거 이해 못하면 접어야한다.
근데 제대로 알려주는데 없음ㅇㅇ



[사이트를 만들기 위해 필요한 것]

세부적인 데이터 전송 과정
html <form> - servlet

입력(UI) - html, jsp

html에서 데이터를 보내줄 때 받는 입장에선 출처를 알아야하기 때문에 폼 태그를 정의하고

<input name="x" value="3"> 이런 식으로 전달함

그러면 자바에서 request.getParameter("x")으로 전달된 <input name="x">과 비교하여 name키가 동일한지 확인하고 value값은 String으로 처리됨

이후 String 객체로

String A = request.getParameter("name");

으로 value 3을 객체에 저장함(물론 내가 일일히.)



연결 - tomcat 얘(통칭 WAS 웹서버) 쓰면 알아서 해줌. 구동원리만 알면 됨
브라우저에서 페이지를 요청하면 그게 맞는지 확인하고 응답해줌
class파일만 있으면 됨 나머진 매핑으로 요청 받음(/hello)

localhost > ipconfig IPv4(여러 기기에서 접속가능)

servlet(let = 조각, ServerApplicationLet > 여러 문서중 하나만 제공되는 문서 = 현재 실행 중인 html 페이지)

context - 개발 시 webapps\root 폴더에서만 다루기 어려워, 따로 나눠서 개발하고 싶을 때 가상 경로만들어 개발함 webapps\contextFile (xml에서 설정 > META-INFO 권장)
root파일에 없지만 root파일에 있는것처럼 씀

Node.js/Tomcat

계산 - java

요청과 응답으로 나눔
요청: 브라우저(크롬) > 서버(톰캣)
응답: 서버 > 브라우저

HttpServlet의 시스템을 가져와 빌려 씀(Http는 하나의 연락수단)
service()에서 구현함(보안상 Http > Https)


데이터 저장 - ArrayList, DBMS
DB 연동 대신 ArrayList 사용 가능



# MyJavaNote


사전 지식

클라이언트가 문서 요청 시 네트워크를 통해 서버에서 만들어서 보냄(기원)
이전에 직접 문서를 수정함 > 자동화 이전 > 수정 할 때마다 다시 다운받음





사이트를 만들기 위해 필요한것

입력 - html, jsp
자바로 페이지 구현 한번만 함.
이후 따로 툴 써서 해결

연결 - tomcat 얘(통칭 WAS) 쓰면 알아서 해줌. 구동원리만 알면 됨
요청에 따른 페이지를 응답해줌

계산 - java, servlet(let = 조각, ServerApplicationLet > 여러 문서중 하나만 제공하는 시스템을 servlet)
HttpServlet 시스템을 가져와 빌려 씀(Http는 하나의 연락수단)
요청과 응답으로 나눔
요청 브라우저(크롬) > 서버(톰캣)
응답 서버 > 브라우저


데이터 저장 - arraylist, DBMS
DB연동 대신 ArrayList 사용 가능(학습용)



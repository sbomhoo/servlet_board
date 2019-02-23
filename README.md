# servlet_board
MVC MODEL2 방식을 이용한 jsp/servlet을 이용한 게시판 만들기
 
***

**<게시판 구현 기능>**
-  게시글 입력,수정,삭제
-  페이징 처리
-  글 입력시 사진 업로드
-  원글에 답변글 달기

***

**<개발 환경>**
- eclipse
- apache-tomcat-8.0.46
- oracle 11g:xe

**<WEB-INF/lib 추가>**
-  cos.jar  //사진 업로드를 위한 라이브러리
-  jstl.jar //jstl
-  standard.jar //EL
-  ojdbc.jar  //oracle db

**<server.xml 데이터베이스 커넥션 풀 추가 내용>**
```html
<Context docBase="web_study_11" path="/web_study_11" reloadable="true" source="org.eclipse.jst.jee.server:web_study_11">
<Resource auth="Container" driverClassName="oracle.jdbc.driver.OracleDriver" loginTimeout="10" maxActive="50" maxIdle="20" 
  maxWait="5000" name="jdbc/myoracle" password="db비밀번호" testOnBorrow="true" type="javax.sql.DataSource"
  url="jdbc:oracle:thin:@127.0.0.1:1521:XE" username="db아이디"/>
  </Context>
```

**<DB 쿼리문>**
<pre><code>create table board(
num number(5) primary key,
pass varchar2(30),
name varchar2(30),
email varchar2(30),
title varchar2(50),
content varchar2(1000),
readcount number(4) default 0,
img varchar2(100),
ref number(5) default 0,
indent number(5) default 0,
step number(5) default 0,
writedate DATE DEFAULT sysdate
);

create sequence board_seq  start with 1 increment by 1;
</code></pre>


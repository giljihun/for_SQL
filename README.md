# SQL (with. MySQL)

SQL 코딩테스트, PCSQL 자격증을 위한 SQL 내용정리입니다. with MySQL

<p align="center"><img src="https://github.com/giljihun/for_SQL/assets/75918176/e4c12bad-ba7a-42fd-a583-5751048fb5f8" width="30%">

**📢 Egoing Lee님의 [mySQL 강의][mysql]를 기반으로 정리합니다**  

[mysql]: https://www.inflearn.com/course/mysql-%EA%B0%95%EC%A2%8C
  
<br></br>    

# 목차 
**[개념]**
- [1. 데이터베이스 개요](<./데이터베이스개요.md>)
- [2. 클라이언트(mysql monitor)란?](<./클라이언트(mysql monitor).md>)
- [3. 테이블이란?](<./테이블.md>)
- [4. 데이터 관리(methods)](<./데이터관리.md>)

**[문제]**
- 추가예정
  
<br></br> 
# mySQL 설치(with M1 and homebrew)
***M1 기준으로 본 문서는 작성됨.***

## 설치
1. 먼저 homebrew 업데이트를 업데이트 해준다.
   (homebrew 설치는 검색 고고)
~~~
$ brew update
~~~

2. MySQL을 설치한다.
~~~
$ brew install mysql
~~~

3. MySQL을 스타트.
~~~
$ mysql.server start
~~~

4. 아래처럼 기본 설정에 대한 질문이 순서대로 나오는데 입맛대로 설정해준다.
```
$ mysql_secure_installation

- 비밀번호 복잡도 검사 과정
- 비밀번호 입력, 재확인 (루트 암호 설정) 
- 익명 사용자 삭제 (익명의 계정을 허용할 것인가)
- 원격 접속 허용하지 않을 것인가?
- test DB 삭제 (기본적으로 생성하는 test DB)
- previlege 테이블을 다시 로드? (현재까지 내용 저장?)
```

완료하면 **All done!** 메시지가 출력됨..//

5. MySQL 사용하기!
~~~
$ mysql -u root -p (이후 설정한 비밀번호 입력)
~~~
<img src="usingIMG/image.png" width="80%">


위 사진처럼 뜨면 완료!
**CHEERS!**

![Alt text](/usingIMG/image-1.png)

ESCAPE 하는 법 : \q 

**return : Bye.**


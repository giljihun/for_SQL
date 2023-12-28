# 데이터베이스 클라이언트

 mySQL 클라이언트는 매우 다양하다.

- mysql-monitor

- mysql query browser

- phpMyAdmin

- navicat

## mysql monitor
(MySQL이 설치된 환경에는 어디든 설치되어있음.)

### 사용법
> mysql -u아이디 -p비밀번호  
> mysql -h 호스트주소 -p 포트번호 -u 아이디 -p 비밀번호
>

![Alt text](/usingIMG/image-2.png)

위처럼 mysql -uroot -p1445로 접속했다.
접속에 성공하면 사진처럼 화면이 구성됨.

~~~sql
mysql> CREATE DATABASE music CHARACTER SET utf8 COLLATE utf8_general_ci;

Query OK, 1 row affected, 2 warnings (0.01 sec)
~~~
music이라는 데이터베이스 생성.

~~~sql
mysql> show databases;

+--------------------+
| Database           |
+--------------------+
| information_schema |
| music              |
| mysql              |
| performance_schema |
| sys                |
+--------------------+

5 rows in set (0.00 sec)
~~~
show databases;를 하면 내 호스트의 데이터베이스 목록을 다 볼 수 있음.  
기존의 DB들과 내가 만든 music이 보임!

~~~sql
mysql> use music;
Database changed
~~~

자 그럼 여기서 우린 music 데이터베이스를 조작하고 싶기 때문에 use를 써서  
music 데이터베이스에 접근해줄거임.  
그러면 Database changes. 라고 뜸.

~~~sql
mysql> CREATE TABLE `favorite_music` (
    ->   `title` varchar(255) NOT NULL,
    ->   `musician` varchar(20) NOT NULL,
    ->   `duration` varchar(20) NOT NULL,
    ->   `album` varchar(30) NOT NULL
    -> ) ENGINE=InnoDB;

Query OK, 0 rows affected (0.01 sec)
~~~
그리고 'favorite_music' 이라는 테이블을 만들어줬음!  
주의해야할 점이, **'** <<- 이런 따옴표가 아니라   
**`** <<- 이런 '백틱'이라고 불리는 걸 사용함. (특정 상황 제외)

~~~sql
mysql> show tables;

+-----------------+
| Tables_in_music |
+-----------------+
| favorite_music  |
+-----------------+

1 row in set (0.00 sec)
~~~
그리고 music의 테이블엔 뭐가 있는 지 확인!

~~~sql
mysql> insert into favorite_music (`title`,`musician`, `duration`, `album`) values('Chasing Pavements', '아델', '3:30', 19);

Query OK, 1 row affected (0.00 sec)

mysql> select * from favorite_music;
+-------------------+----------+----------+-------+
| title             | musician | duration | album |
+-------------------+----------+----------+-------+
| Chasing Pavements | 아델     | 3:30     | 19    |
+-------------------+----------+----------+-------+
1 row in set (0.00 sec)
~~~
insert를 통해서 테이블에 값을 넣어줍시다. row를 추가해주는 것.  
그리고 select를 통해 페이보릿뮤직에 뭐가 있는 지도 확인해보았음!! 잘들어간 모오습.

~~~sql
mysql> select * from favorite_music;
+-------------------+-----------+----------+---------------+
| title             | musician  | duration | album         |
+-------------------+-----------+----------+---------------+
| Chasing Pavements | 아델      | 3:30     | 19            |
| 서른즈음에        | 김광석    | 3:30     |               |
| All 4 Nothing     | Lauv      | 3:04     | All 4 Nothing |
+-------------------+-----------+----------+---------------+
3 rows in set (0.00 sec)
~~~
현재 카톡 프뮤인 Lauv - All 4 Nothing도 넣어봤음 ㅎㅎ.
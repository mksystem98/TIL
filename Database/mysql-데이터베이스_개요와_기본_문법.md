# MySQL- 데이터베이스 개요와 기본 문법





## Database란 무엇인가? 

- 구조화된 데이터의 집합체



## DBMS(Database Management System)

- 데이터베이스와 사용자 간의 인터페이스 역할을 하는 소프트웨어
- 데이터베이스의 등록,수정,삭제,조회,검색 등 여러가지 도구를 제공함



DBMS 는 RDBMS(관계형 데이터베이스 관리 시스템)와 NoSQL(비관계형 데이터베이스)로 나눌 수 있다.

- **RDBMS**
    - 특징: 데이터를 테이블 형태로 저장하며, 테이블 간의 관계를 통해 데이터를 조직
    - 예: Oracle, MySQL, PostgreSQL 등
- **NoSQL**
    - 특징: 빠른 읽기/쓰기의 속도, 덜 엄격한 스키마
    - 예: MongoDB, Redis 등



## SQL(Structured Query Language)

- 관계형 데이터베이스를 관리하기 위한 표준 프로그래밍 언어
- 데이터베이스에서 데이터를 조회, 삽입, 수정, 삭제 등을 수행하는 데 사용됨



## MySQL

- 오픈 소스 관계형 데이터베이스 관리 시스템(RDBMS)
- SQL 언어를 사용하여 데이터베이스와 소통하며, 웹 애플리케이션에서 널리 사용됨



## 왜 RDBMS를 선택했는가 ? 

- 백엔드 개발자 취업 공고에서 NoSQL보다 RDBMS의 수요가 더 많다
- 인터넷 강의, 도서 등 정보를 얻기가 더 수월하였음



-------------------------

# 기본 문법

> SQL에는 SHOW, DROP, CREATE 같은 여러가지 **키워드**가 존재한다. SQL은 대소문자를 구분하지 않는 언어이기 때문에 
>
> 키워드를 소문자로 작성해도 기술적으로는 문제가 없으나, 가독성 향상과 많은 개발자와 문서에서 대문자를 사용하는 
>
> 관례를 따르고 있기 때문에 **키워드는 대문자로 사용하는 것을** 권장한다.

<br>



### 데이터베이스 생성

```mysql
CREATE 데이터베이스이름;
```



### 생성된 데이터베이스 표시

```mysql
SHOW databases;
```

<img width="420" alt="capture 28" src="https://github.com/mksystem98/TIL/assets/147119824/5bc82246-a46e-421d-8690-7d13605655c2">

> information_schema, mysql, performance_schema, sys 데이터베이스는
>
>  MySQL을 설치할 때 기본적으로 생성된다. 



<br>



### 데이터베이스 사용

생성된 여러 가지 데이터베이스 중에 작업하고자 하는 특정 데이터베이스를 선택한다.

MySQL과 같은 관계형 데이터베이스 관리 시스템에서는 한 번에 하나의 데이터베이스만 선택할 수 있다.

```mysql
USE 데이터베이스이름;
```



<br>



## 테이블(table)

테이블이란, 열(column)과 행(row)으로 구성된 구조를 가지며 이를 통해 데이터를 구조화된 형태로 저장한다. 

<img width="400" alt="capture 29" src="https://github.com/mksystem98/TIL/assets/147119824/f98d2192-3154-4d9b-81a0-19e56bfc60d8">

강아지의 정보를 저장하는 'dogs' 테이블을 만들어 보았다. 

열(파란색 박스)를 통해 name, age, breed 처럼 다양한 속성을 열로 가질 수 있다. 

행(노란색 박스)는 실제 입력된 데이터이다. 첫 번째 행에서는 name은 'happy', age는 3, breed는 'Bulldog' 로 데이터가 입력되었다.

<br>



### 데이터 형식

데이터베이스에서 테이블을 구성할 때, 각 열에는 특정 데이터 형식이 지정된다. 

예를 들어, 'name'열에는 문자열(string)만 저장할 수 있도록, 'age' 열에는 정수형(integer)만 입력되도록 설정할 수 있다. 

이러한 데이터 형식을 지정하는 이유는 데이터의 일관성과 정확성을 유지하기 위함이다.


<br>



데이터 형식을 알맞게 지정하지 않고 데이터를 입력하는 경우를 예로 들어보자.

age열에 '3', '4', 'maybe..6' 과 같이 일관되지 않은 형식의 데이터가 저장되어 있다면, 업데이트 작업이 어려워지고 데이터의 정확성이 손상될 수 있을 것이다.

반면 age열에 Integer 타입을 지정하여 1, 2, 5, 6 과 같이 일관된 형식의 데이터를 저장한다면, 나이를 1년씩 증가시키거나 감소시키는 등 작업을 간단하고 일관되게 수행할 수 있을 것이다. 



> 테이블을 생성하고 특정 데이터형을 지정해보기 전에,  **숫자형 데이터** 형식은 **INT(정수형)**를, 
>
> **문자열 데이터** 형식은 **VARCHAR(가변 문자열)** 형식을 사용할 것이다. 
>
> 더 많은 데이터 형식은 차차 알아나갈 것이다.
>
> [MySQL Data Types 공식 문서](https://dev.mysql.com/doc/refman/8.0/en/data-types.html)



<br>



### 테이블 생성

테이블을 생성할 때, 각 열(column)에 대해 데이터 타입을 명시해주어야 한다.

```mysql
CREATE TABLE dogs (
	name VARCHAR(20), -- 문자열의 길이를 50글자로 지정함.
	age INT,
	breed VARCHAR(20)
);
```



<br>



### 테이블 생성 확인

```mysql
SHOW tables;
```

<img src="https://github.com/mksystem98/TIL/assets/147119824/b4b68e4b-c5f1-46a4-a744-9d613dc444ea" alt="capture 34" style="zoom:160%;" />

<br>



### 테이블의 상세 항목 확인

```mysql
SHOW COLUMNS FROM 테이블이름;
          또는
DESC 테이블이름;
```

<img src="https://github.com/mksystem98/TIL/assets/147119824/515cecff-a782-4284-9ba6-16d189e36983" alt="image" style="zoom:106%;" />

테이블의 상세 항목을 확인할 수 있다. Null, Key, Default, Extra 항목에 대해서는 진도를 나가며 알아볼 것이다. 



<br>

### 테이블 제거

```mysql
DROP TABLE 테이블이름;
```



<br>



## 주석

주석은 명령문 안에서 설명 또는 메모를 추가하는 데 사용되며, 코드를 실행해도 주석된 문장을 실행되지 않는다.

### 단일 행 주석

```mysql
-- mk_system 데이터베이스를 사용하는 쿼리입니다.
USE mk_system;
```



<br>



### 다중 행 주석

```mysql
/*
테이블을 삭제하는 명령어입니다.
삭제하기 전, 중요한 데이터가 있는지 꼭 확인하세요. 
*/
DROP TABLE dogs;
```





<br>

## 데이터 삽입 

테이블에 데이터를 단일 또는 다중으로 삽입할 수 있다.

### 데이터 삽입 - 단일 

```mysql
INSERT INTO dogs (name, age, breed)
VALUES ('happy', 3, 'Bulldog');
```

<br>

### 데이터 삽입 - 다중

```mysql
INSERT INTO dogs (name, age, breed)
VALUES 
	('kong', 4, 'Poodle')
	('choco', 1, 'Maltest');
```

<br>

## 테이블의 데이터 조회

'SELECT' 키워드를 통해 테이블에서 데이터를 조회할 수 있다.

<br>

### 테이블의 모든 행 표시

```mysql
SELECT * FROM 테이블이름;
```

<img width="330" alt="image" src="https://github.com/mksystem98/TIL/assets/147119824/ee3e6179-c6bf-49a0-bcf2-2781922e5f84">

<br>

### 테이블의 특정 열만 표시

```mysql
SELECT age FROM dogs;
```

<img width="330" alt="image" src="https://github.com/mksystem98/TIL/assets/147119824/f14a4d1e-9baa-4bdf-968e-134bde110f76">

<br>



### 테이블의 특정 열 여러 개 표시

```mysql
SELECT name, breed FROM dogs;
```

<img width="376" alt="image" src="https://github.com/mksystem98/TIL/assets/147119824/f17f94c6-a43c-4c01-95ef-aafabc6bb3bf">

<br>



## NULL 과 NOT NULL



위에서 만들었던 dogs 테이블의 상세 정보(`SHOW COLUMNS FROM dogs`)를 살펴보면, NULL 열이 YES로 되어있는 것을 확인할 수 있다. 이는 'name', 'age', 'breed' 열에 NULL 값을 넣을 수 있다는 의미이다. 

![capture 44](https://github.com/mksystem98/TIL/assets/147119824/facd01f6-90e0-4346-bee4-191648388981)



> **NULL 이란 ?**
>
> 'NULL'은 필드가 빈 상태이거나 값이 알려지지 않았음을 의미한다. 0이나 빈 문자열("")과는 다르다.
>
> 추가적인 예제로 밑에서 설명할 것이다.

<br>

```mysql
INSERT INTO dogs (name)
VALUES ('wow');
```

이처럼 'dogs' 테이블에 age, breed 열에는 아무런 데이터를 넣지 않고 name열에만 데이터를 삽입하였다. 이렇게 하면, age, breed 열에는 'NULL' 값이 들어가게 된다. 확인을 해보자.

<br>

<img width="330" alt="image" src="https://github.com/mksystem98/TIL/assets/147119824/a79ccb8c-0b4c-4e18-ac1a-5c3acef3b141">

age 열과 breed 열에 'NULL' 값이 할당되어 있는 것을 확인할 수 있다. 어떻게 'NULL'값을 넣을 수 있었을까 ?

그 이유는 테이블을 생성할 때 'NULL'에 대한 기본적인 설정값이 허용으로 되어있기 때문이다. 'NULL' 값이 입력되길 원치 않다면 테이블을 생성할 때 'NOT NULL' 처리를 해주어야 한다.

<br>

### NOT NULL

```mysql
CREATE TABLE dogs2 (
	name VARCHAR(20) NOT NULL,
  age INT NOT NULL
);
```

이렇게 테이블을 생성할 때 해당 열에 'NOT NULL ' 제약 조건을 추가해 주어야 'NULL'값이 들어가지 않도록 막을 수 있다. 

<br>

```mysql
INSERT INTO dogs2 (name, age)
VALUES ('abc');  -- age에 값을 할당하지 않았음. 

-- age열은 NOT NULL이므로 에러 발생
ERROR 1136 (21S01): Column count doesn't match value count at row 1
```

이처럼, 'NOT NULL' 제약 조건을 위반하면 오류가 발생하게 된다. 또다른 예를 들자면 회원가입 시스템 구축에서의 이름, 이메일, 휴대폰 번호 등 필수 정보는 누락되면 안 되므로 'NOT NULL' 제약 조건을 설정할 수 있을 것이다. 



<br>

## 기본값 설정 -  DEFAULT

'DEFAULT' 제약 조건은 테이블의 특정 열에 대한 기본값을 설정하는 데 사용된다.

해당 열에 명시적인 값이 제공되지 않았을 경우 사용되는 값을 설정한다. 

```mysql
CREATE TABLE dogs3 (
    name VARCHAR(50) NOT NULL,
    breed VARCHAR(50) DEFAULT 'Unknown',  -- 기본값 설정
    age INT 
);
```

```mysql
INSERT INTO dogs3 (name, age)
VALUES 
	('coco', 3),
	('gold', 6),
	('white', 1);
```

테이블을 생성하고, breed열에 'DEFAULT' 제약조건을 넣어보았다.

<br>

![image](https://github.com/mksystem98/TIL/assets/147119824/63cd6239-2834-4a35-a944-30fcbfff7373)

'breed' 열에 아무런 값도 주지 않아도 'DEFAULT' 제약조건 때문에 기본값으로 'Unknown'이 들어간 모습이다. 

이처럼 'DEFAULT' 제약조건은 테이블의 특정 열에 대해 항상 값을 갖도록 하고자 할 때 유용하다.

<br>

## 기본키 -  Primary Key

사람의 이름과 나이를 저장하는 human 테이블을 생성해보았다.

![capture 46](https://github.com/mksystem98/TIL/assets/147119824/86342cdc-6930-40fb-af5b-c505710f20d8)

테이블 정보에서 보이는 'Key' 열은 무엇을 의미하는 열인지 알아보도록 하자.

<br>

![image](https://github.com/mksystem98/TIL/assets/147119824/155e93e2-6fb9-4260-a393-b6d6097c9f4d)

name은 'Kim', age는 20의 값을 가진 동일한 6행의 데이터를 삽입해보았다. 이 동일한 값의 행들은, 관리하거나 분간하기 정말 어려워질 것이다. 

이러한 데이터가 있다면 일종의 **고유 식별자**를 추가하여 구분할 수 있게 해야 한다. 이 때, **Primary Key(기본키)**를 사용할 수 있다.

```mysql
CREATE TABLE unique_human (
	human_id INT PRIMARY KEY,
	name VARCHAR(30) NOT NULL,
	age INT NOT NULL
);

       or
       
CREATE TABLE unique_human2 (
	human_id INT ,
	name VARCHAR(30) NOT NULL,
	age INT NOT NULL,
  PRIMARY KEY (human_id)
);
```

이렇게 human_id 열을 'Primary Key'로 선언함으로써 인해 각 행을 고유하게 식별할 수 있다. 제품의 바코드나 시리얼 번호 같은 것이다.

```mysql
INSERT INTO unique_human (human_id, name, age)
VALUES
	(1, 'Kim', 20),
	(2, 'Kim', 20),
	(3, 'Kim', 20);
```

![image](https://github.com/mksystem98/TIL/assets/147119824/d8fc5d95-db72-4692-8eff-6c04a2b3f26f)



<br>

### AUTO_INCREMENT

하지만, 이렇게 수작업으로 'Primary Key'에 대한 값을 계속 넣어주는 것은 번거롭다. 

이를 **AUTO_INCREMENT**를 선언함으로써 해결할 수 있다. 

```mysql
CREATE TABLE unique_human3 (
	human_id INT AUTO_INCREMENT,  -- AUTO_INCREMENT 선언
  name VARCHAR(30) NOT NULL,
  age INT NOT NULL,
  PRIMARY KEY (human_id)
);
```

```mysql
INSERT INTO unique_human3 (name, age)
VALUES
	('LEE', 20),
	('LEE', 20),
	('LEE', 20);
```

테이블에 값을 삽입할 때, human_id는 제외하고 동일한 3개의 행을 삽입하였다.

<br>

![image](https://github.com/mksystem98/TIL/assets/147119824/78c91f8f-81a1-49f0-af3d-5d1ab1617ee2)

이처럼, 테이블에 새로운 행이 추가될 때마다, 'AUTO_INCREMENT'로 설정된 열의 값은 **자동으로 증가**하여 각 행이 고유한 식별자를 가지게 한다. 이를 통해 개발자는 각 행의 고유성을 수동으로 관리하지 않아도 되므로 생산성을 높일 수 있게 된다.

<br>



## CRUD

CRUD는 데이터를 처리하는 기본적인 네 가지 작업을 뜻하는 용어이다. SQL에서만아니라 프로그래밍에서 널리 적용되고 있다. 

### 1. Create (생성)

- 데이터를 생성하고 데이터베이스에 추가하는 작업
- '**CREATE**'문으로 데이터베이스와 테이블을 생성
- '**INSERT**'문을 사용하여 새로운 데이터(행)을 테이블에 추가

<br>

### 2. Read (읽기)

- 데이터를 조회하고 읽는 작업

- '**SELECT**'문을 사용하여 데이터를 조회

- '**WHERE**'문을 사용하여 행의 범위를 좁혀 조회할 수 있다. 행을 업데이트 하거나 삭제할 때도 사용됨

    - ```mysql
        -- breed가 'Bulldog'인 행 조회
        SELECT * FROM dogs WHERE breed = 'Bulldog';
        
        -- age가 4인 행 조회
        SELECT * FROM dogs WHERE age = 4;
        ```

<br>

### 3. Update (갱신)

- 데이터베이스의 기존 데이터를 수정하는 작업

- **'UPDATE'** 문을 사용하여 데이터를 갱신

- ```mysql
    -- UPDATE 테이블_이름 SET 의 문법으로 사용
    -- breed가 'Poodle'인 강아지를 'Mix'로 변경
    UPDATE dogs SET breed = 'Mix' WHERE breed = "Poodle";
    
    -- name이 'happy'인 강아지의 나이를 5살로 변경
    UPDATE dogs SET age = 5 WHERE name = 'happy';
    ```

<br>

### 4. Delete (삭제)

- 데이터베이스에서 데이터를 삭제하는 작업

- **'DELETE'**문을 사용하여 데이터를 삭제

- ```mysql
    -- 이름이 'happy'인 고양이 삭제
    DELETE FROM dogs WHERE name = 'happy';
    
    -- dogs 테이블의 모든 행 삭제
    DELETE FROM dogs;
    ```

<br>

### Alias(AS) - 별칭 부여

**'AS'** 명령어를 이용해 열이나 테이블에 별칭을 부여하는데 사용되며, 실제 열의 이름이 바뀌는 것이 아니라 결과를 이해하기 쉬운 형태로 표시하는 것이다.

```mysql
-- human_id 열을 id로 표시, 실제 열 이름이 변경되는 것은 아님.
SELECT human_id AS id, name, age FROM unique_human;
```

<img src="https://github.com/mksystem98/TIL/assets/147119824/1d471f0e-fb60-4503-bc6a-ca5703330f8a" alt="capture 50" style="zoom:130%;" />



----------------------------

## 

## 문자열 함수

데이터를 처리할 때, 여러 문자열을 하나로 결합하거나, 특정 부분을 추출하고 대체하는 등 다양한 작업을 수행해야 하는 경우가 있다. MySQL에서는 이러한 작업들을 간단하고 효율적으로 수행할 수 있도록 다양한 문자열 함수를 제공하고 있다. 

[MySQL - String Functions 공식 문서](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html)

<br>

문자열 함수를 다루기 위해 'movie' 테이블을 생성해 보았다.

```mysql
CREATE TABLE movies(
	movie_id INT PRIMARY KEY AUTO_INCREMENT,
  title VARCHAR(50),
  director_fname VARCHAR(50),
  director_lname VARCHAR(50),
  released_year INT,
  runtime INT,
  language VARCHAR(50)
);
```

```mysql
INSERT INTO movies (title, director_fname, director_lname, released_year, runtime, language)
VALUES 
	('Parasite', 'Junho', 'Bong', 2019, 131, 'Korean'),
	('Oldboy', 'Chanwook', 'Park', 2003, 120, 'Korean'),
	('Monster', 'Hirokazu', 'Koreeda', 2023, 126, 'Japanese'),
	('Love Letter', 'Shunji', 'Iwai', 1995, 117, 'Japanese'),
	('ReQuiem', 'Darren', 'Aronofsky', 2000, 101, 'English');
```

<br>

### CONCAT - 문자열 결합

'CONCAT(Concatenate)' 함수를 사용해 문자열을 하나로 결합할 수 있다.

```mysql
SELECT CONCAT('Hello', ' ', 'World');
-- 결과는 'Hello World'
```

```mysql
SELECT CONCAT(director_fname, ' ', director_lname) AS author_name FROM movies;
```

<img src="https://github.com/mksystem98/TIL/assets/147119824/26740441-3838-4e36-afba-c0f10b2fbb7a" alt="image" style="zoom:105%;" />

<br>

### CONCAT_WS(CONCAT With Separator)

이 함수는  'CONCAT'처럼 문자열을 결합하는 기능을 갖고 있는데, 다른 점은 구분자가 사용되어 결합되는 각 문자열 사이에 삽입된다. 

```mysql
SELECT CONCAT_WS('-', title, director_fname, director_lname) FROM movies;
```

![image](https://github.com/mksystem98/TIL/assets/147119824/389555d6-13d1-4bd8-8956-7e432acc321f)

<br>

### SUBSTRING() / SUBSTR() - 문자열 추출

'SUBSTRING() / SUBSTR()' 함수는 문자열을 추출하는 함수이다. 

```mysql
SELECT SUBSTR('Hello World', 1, 5);  -- 1번째 문자부터 5번째 문자까지 추출 'Hello'
SELECT SUBSTR('Hello World', 8);  -- 8번째 문자부터 출력 'orld'
SELECT SUBSTR('Hello World', -5);  -- 뒤에서부터 5번째 문자 출력 'World'
```

```mysql
SELECT SUBSTR(title, 1, 3) AS 'short title' FROM movies;
```



<br>

### REPLACE - 문자열 대체

'REPLACE' 함수는 특정 부분 문자열을 다른 문자열로 대체한다.

```mysql
REPLACE ('원본_문자열', '대체하고자_하는_부분', '대체할_새로운_문자열');
```

```mysql
SELECT REPLACE('1 2 3 4', ' ', ' and ');

-- 1 and 2 and 3 and 4     
```

<br>



### REVERSE - 문자열 뒤집기

'REVERSE' 함수는 문자열을 뒤집는 함수이다.

```mysql
SELECT REVERSE('Hello World');
-- 'dlroW olleH' 

SELECT REVERSE('MySQL is good');
-- 'doog si LQSyM'   
```



<br>

### CHAR_LENGTH - 문자열 길이 반환

'CHAR_LENGTH' 함수는 문자열의 길이를 문자의 수로 반환한다.

```mysql
SELECT CHAR_LENGTH('Hi MySQL');
-- 8(공백을 포함하여 반환한다.)
```

<br>

### UPPER/LOWER - 대/소문자 변경

'UPPER' 함수는 주어진 문자열을 모두 대문자로 변환한다.

```mysql
SELECT UPPER('Hi MySQL');
-- 'HI MYSQL'
```

<br>

'LOWER' 함수는 주어진 문자열을 모두 소문자로 변환한다.

```mysql
SELECT LOWER('Hi MySQL');
-- 'hi mysql'
```

<br>

### TRIM - 공백 제거

'TRIM' 함수는 문자열의 양쪽 끝에 있는 공백을 제거하는 데 사용되며, 문자열 내부의 공백은 제거하지 않는다.

```Mysql
SELECT TRIM('   Hi MySQL     ');
-- 'Hi MySQL'
```





-------------------------------------


















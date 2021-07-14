## SQL 언어

- SQL도 프로그래밍 언어다. (Database에 대한 프로그래밍 언어)

- 대소문자를 구분하지 않는다. (파이썬은 대소문자 구분)

  - 관용적으로 `키워드`는 대문자를 이용한다.

  

### 기본 문법

- cmd에서 `> myssqld`: MySQL 진입

- MySQL console에서 `> mysql -u python -p`

- `mysql > show database;`: 지금 어떤 데이터베이스가 있는지 보여줘
- `mysql > use library;` : library라는 데이터베이스에서 작업할래
- `mysql > show tables;` : table 조회



### Toad (IDE)

이렇게 command 기반으로 MySQL을 이용할 수도 있지만, 일반적으로는 IDE를 이용해서 database 사용!

- Toad 의 Toad Edge for MySQL 사용
- python으로 만들어둔 계정으로 연결했음

<img src="C:\Typora image\image-20210709100824936.png" alt="image-20210709100824936" style="zoom: 67%;" />





# MySQL

- 데이터 타입
  - `VARCHAR` : 문자열
  - `INT` : 숫자

- record == row == 행, column으로 된 구조다.

- column별로 제약을 건다

- **제약 (Constraints)**:

  - `NOT NULL` : 빈 값이 아니다

  - `UNIQUE` : 겹치지 않다

  - `PRIMARY KEY` : 빈 값이 아니며(`NOT NULL`) + 겹치지 않는다(`UNIQUE`)

    - 단일키, 중복키, 복합키
    - 해당 table  내에서 <u>유일하게 record를 식별</u>할 수 있다.
    - [Eg] 주민등록번호

  - `FOREIGN KEY` 

    - 대부분 다른 테이블을 참조할 때 그 테이블의 primary key를 foreign key로 설정

      ![image-20210709111550055](C:\Typora image\image-20210709111550055.png)


# Oracle Database Query

## 1. 테이블 생성

    CREACT TABLE [테이블명] (
      [컬럼명] [데이터타입] [제약조건...]
      id VARCHAR2(12) NOT NULL,
      blackCnt NUMBER(1) DEFAULT 0,
      joinDt Date NOT NULL,
      CONSTRAINT PK PRIMARY KEY (id)
    )

> 데이터타입<br>

- VARCHAR2(10): 10byte 가변 길이 문자열<br>
- NUMBER(2): 2자리의 가변 길이 정수<br>
- NUMBER(4, 2): 4자리의 가변 길이 정수 및 2자리의 가변길이 소수<br>
- ...<br>

> 제약조건<br>

- NOT NULL: null 값 불가<br>
- DEFAULT [value]: [value]로 초기값 설정<br>
- ...<br>

> key 생성<br>

- CONSTRAINT [제약조건 이름] PRIMARY KEY ([컬럼명]): PK 생성<br>

---

## 2. 테이블 설명 생성

    COMMENT ON TABLE [테이블명] IS '[테이블 설명]';

---

## 3. 컬럼 설명 생성

    COMMENT ON COLUMN [테이블명].[컬럼명] IS '[컬럼 설명]';

---

## 4. 인덱스 생성

    CREATE INDEX [인덱스명] ON [테이블명]([컬럼명1], [컬럼명2], ...);

---

## 5. 데이터 삽입

> 특정 컬럼만 선택적으로 명시하여 데이터 삽입

    INSERT INTO [테이블명] ([컬럼명1], [컬럼명2], ...) VALUES([value1], [value2], ...);

> 컬럼을 생략하여 모든 컬럼에 해당하는 값 삽입

    INSERT INTO [테이블명] VALUES([value1], [value2], ...);

> SELECT를 통한 데이터 삽입

    INSERT INTO [테이블명1] ([컬럼명1], [컬럼명2], ...) SELECT * FROM [테이블명2]

---

## 6. 데이터 갱신

    UPDATE
      [테이블명]
    SET
      [컬럼명1] = '[value1]'
      , [컬럼명2] = '[value2]'
      , ...
    WHERE
      [컬럼명3] = '[value3]'

---

## 7. 테이블 컬럼 추가

    ALTER TABLE [테이블명] ADD([컬럼명] [데이터타입]);

---

## 8. 테이블 컬럼 수정 (데이터 타입, 기본값, 제약조건)

> 데이터 타입

    ALTER TABLE [테이블명] MODIFY [컬럼명] [데이터타입];

> 기본값

    ALTER TABLE [테이블명] MODIFY [컬럼명] DEFAULT [value];

> 제약조건

    ALTER TABLE [테이블명] MODIFY [컬럼명] [NOT NULL / NULL];

> 한번에

    ALTER TABLE [테이블명] MODIFY [컬럼명] [데이터타입] DEFAULT [value] [NOT NULL / NULL];

---

## 9. 테이블 컬럼 삭제

    ALTER TABLE [테이블명] DROP COLUMN [컬럼명];

---

## 10. 테이블 컬럼명 변경

    ALTER TABLE [테이블명] RENAME COLUMN [ASIS컬럼명] TO [TOBE컬럼명];

---

# Oracle Database Query

## 테이블 생성

    CREACT TABLE [테이블명] (
      [컬럼명] [데이터타입] [제약조건...]
      id VARCHAR2(12) NOT NULL,
      blackCnt NUMBER(1) DEFAULT 0 NOT NULL,
      joinDt Date NOT NULL,
      CONSTRAINT PK PRIMARY KEY (id)
    )

### 데이터타입<br>

- VARCHAR2(10): 10byte 가변 길이 문자열<br>
- NUMBER(2): 2자리의 가변 길이 정수<br>
- NUMBER(4, 2): 4자리의 가변 길이 정수 및 2자리의 가변길이 소수<br>
- ...<br>

### 제약조건<br>

- NOT NULL: null 값 불가<br>
- DEFAULT [value]: [value]로 초기값 설정<br>
- ...<br>

### key 생성<br>

- CONSTRAINT [제약조건 이름] PRIMARY KEY ([컬럼명]): PK 생성<br>

---

## 테이블 설명 생성

    COMMENT ON TABLE [테이블명] IS '[테이블 설명]';

---

## 컬럼 설명 생성

    COMMENT ON COLUMN [테이블명].[컬럼명] IS '[컬럼 설명]';

---

## 인덱스 생성

    CREATE INDEX [인덱스명] ON [테이블명]([컬럼명1], [컬럼명2], ...);

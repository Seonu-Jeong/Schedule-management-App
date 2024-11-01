# 스케줄 관리 앱 만들기

## 목차

1. [ERD](#ERD)
2. [API 명세서](#API-명세서)

## ERD

![image](https://github.com/user-attachments/assets/a78adff3-1cb9-4dc9-b01f-a0da74e2d2a1)

## API 명세서

<!--일정 생성-->
<details>
<summary>일정 생성</summary>

### 기본정보

| 메서드 |      URL      | 인증방식 |
| :----: | :-----------: | :------: |
|  POST  | /api/schedule | 비밀번호 |

### 요청 바디

|   이름    |   설명   | 필수 |
| :-------: | :------: | :--: |
| user_name | 작성자명 |  O   |
|   todo    |  할 일   |  O   |
| password  | 비밀번호 |  O   |

### 응답

| 상태 코드 |   설명    |
| :-------: | :-------: |
|    201    | 정상 등록 |


</details>

<!--전체 일정 조회-->
<details>
<summary>전체 일정 조회(등록된 일정 불러오기)</summary>

### 기본정보

| 메서드 |      URL      | 인증방식 |
| :----: | :-----------: | :------: |
|  GET   | /api/schedule |   없음   |

## 요청

### 쿼리 파라미터

|       이름        |   설명   | 필수 |
| :---------------: | :------: | :--: |
|    author_name    | 작성자명 |  O   |
| modification_date |  수정일  |  X   |

## 응답

### 본문

|     이름      |    타입    |      설명      |
| :-----------: | :--------: | :------------: |
| schedule_list | Schedule[] | 일정 정보 목록 |

### Schedule

|        이름        |  타입  |  설명  |
| :----------------: | :----: | :----: |
|        todo        | String | 할 일  |
|   creation_date    | String | 작성일 |
| modificaition_date | String | 수정일 |

</details>

<!--선택 일정 조회-->
<details>
<summary>선택 일정 조회(선택한 일정 정보 불러오기)</summary>

### 기본정보

| 메서드 |             URL             | 인증방식 |
| :----: | :-------------------------: | :------: |
|  GET   | /api/schedule/{schedule_id} |   없음   |

## 요청

### 쿼리 파라미터

|    이름     |    설명     | 필수 |
| :---------: | :---------: | :--: |
| schedule_id | 일정 아이디 |  O   |

## 응답

### 본문

|   이름   |   타입   |   설명    |
| :------: | :------: | :-------: |
| schedule | Schedule | 일정 정보 |

### Schedule

|        이름        |  타입  |  설명  |
| :----------------: | :----: | :----: |
|        todo        | String | 할 일  |
|   creation_date    | String | 작성일 |
| modificaition_date | String | 수정일 |

</details>

<!--선택 일정 수정-->
<details>
<summary>선택 일정 수정</summary>

### 기본정보

| 메서드 |             URL             | 인증방식 |
| :----: | :-------------------------: | :------: |
|  PUT   | /api/schedule/{schedule_id} | 비밀번호 |

## 요청

### 쿼리 파라미터

|    이름     |    설명     | 필수 |
| :---------: | :---------: | :--: |
| schedule_id | 일정 아이디 |  O   |

### 바디

|    이름     |   설명   | 필수 |
| :---------: | :------: | :--: |
|    todo     |  할 일   |  X   |
| author_name | 작성자명 |  X   |

## 응답

### 본문

| 상태코드 | 설명      |
| :------: | --------- |
|   201    | 정상 수정 |

</details>

<!--선택 일정 삭제-->
<details>
<summary>선택 일정 삭제</summary>

### 기본정보

| 메서드 |             URL             | 인증방식 |
| :----: | :-------------------------: | :------: |
| DELETE | /api/schedule/{schedule_id} | 비밀번호 |

## 요청

### 쿼리 파라미터

|    이름     |    설명     | 필수 |
| :---------: | :---------: | :--: |
| schedule_id | 일정 아이디 |  O   |

## 응답

### 본문

| 상태코드 | 설명      |
| :------: | --------- |
|   200    | 정상 삭제 |

</details>

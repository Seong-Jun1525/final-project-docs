# 숙박 API 명세서

## 숙박업소 CRUD

| IDX           | 기능명             | 설명                    | Method | API Path             | Request Body / Params                                  | Response Body                       |
| ------------- | ------------------ | ----------------------- | ------ | -------------------- | ------------------------------------------------------ | ----------------------------------- |
| Accommodation | 숙박업소 목록 조회 | 전체 숙박업소 목록 조회 | GET    | /accommodations      | [accomListInfo](#accomimginfo)                         | List<AccomListDTO>                  |
|               | 숙박업소 등록      | 숙박업소 정보 등록      | POST   | /accommodations      | [accomInfo](#accomInfo), [accomImgInfo](#accomImgInfo) | 숙박업소 정보 및 숙박업소 사진 정보 |
|               | 숙박업소 수정      | 숙박업소 정보 수정      | PUT    | /accommodations      | [updatedAccomInfo](#updatedaccominfo)                  | 수정된 숙박업소 정보                |
|               | 숙박업소 삭제      | 숙박업소 정보 삭제      | DELETE | /accommodations      | accomNo                                                | 삭제 결과                           |
|               | 숙박업소 상세 조회 | 특정 숙박업소 상세 조회 | GET    | /accommodations/{id} | 없음                                                   | accomDetailDTO                      |

### accomListInfo

```json
accomListInfo {
  "keyword": "키워드",
  "location": "지역명",
  "checkIn": "체크인날짜",
  "checkOut": "체크아웃날짜",
  "guests": "인원수",
  "page": 0, // 페이지 수
  "size": 0 // 데이터 수
}
```

---

### accomInfo

```json
accomInfo {
  "accomName": "숙박업소명",
  "accomDesc": "숙박업소설명",
  "accomLat": 0, // 위도
  "accomLon": 0, // 경도
  "accomAddr": "주소",
  "accomPhone": "01012345678",
  "pubFacInfo": "공용편의시설정보",
  "inRoomFacInfo": "객실내시설정보",
  "etcFacInfo": "기타시설정보",
  "accomTypeNo": 0 // 숙박유형번호
}
```

### accomImgInfo

```json
accomImgInfo {
  "accomImgOrgName": "이미지원본이름",
  "accomImgChgName": "이미지경로명",
  "accomNo": 0, // 숙박업소번호
}
```

---

### updatedAccomInfo

```json
updatedAccomInfo {
  "accomNo": 0, // 숙박업소번호
  "accomName": "숙박업소명",
  "accomDesc": "숙박업소설명",
  "accomLat": 0, // 위도
  "accomLon": 0, // 경도
  "accomAddr": "주소",
  "accomPhone": "01012345678",
  "pubFacInfo": "공용편의시설정보",
  "inRoomFacInfo": "객실내시설정보",
  "etcFacInfo": "기타시설정보",
  "accomTypeNo": 0 // 숙박유형번호
}
```

<!-- TODO -->

## 객실 CRUD

| IDX           | 기능명         | 설명                | Method | API Path | Request Body / Params | Response Body |
| ------------- | -------------- | ------------------- | ------ | -------- | --------------------- | ------------- |
| Accommodation | 객실 목록 조회 | 전체 객실 목록 조회 | GET    | /        |                       |               |
|               | 객실 등록      | 객실 정보 등록      | POST   | /        |                       |               |
|               | 객실 수정      | 객실 정보 수정      | PUT    | /        |                       |               |
|               | 객실 삭제      | 객실 정보 삭제      | DELETE | /        | accomNo               | 삭제 결과     |
|               | 객실 상세 조회 | 특정 객실 상세 조회 | GET    | //{id}   | 없음                  |               |

## 예약

| IDX         | 기능명                 | 설명                                       | Method | API Path                          | Request Body                     | Response Body |
| ----------- | ---------------------- | ------------------------------------------ | ------ | --------------------------------- | -------------------------------- | ------------- |
| Reservation | 예약 및 결제 정보 조회 | 예약페이지. 예약 정보, 객실정보, 결제 정보 | GET    | /accommodations/{id}/reservations | 객실정보, 예약 정보 및 결제 정보 |               |
| Payment     | 결제승인               | 부트페이를 활용한 결제승인처리             | POST   | /payments/confirm                 | 결제정보                         |               |
|             | 결제단건조회           | 부트페이를 활용한 결제단건조회             | GET    | /payments/{receiptId}             | receiptId                        | 결제정보      |

## 내 예약 내역

| IDX                 | 기능명         | 설명                                       | Method | API Path                        | Request Body | Response Body  |
| ------------------- | -------------- | ------------------------------------------ | ------ | ------------------------------- | ------------ | -------------- |
| Member, Reservation | 예약 내역      | 마이페이지에서 내 예약 정보 조회           | GET    | /members/{id}/reservations      | memberEmail  | 예약 내역 정보 |
|                     | 예약 상세 조회 | 마이페이지에서 특정 예약 상세 정보 조회    | GET    | /members/{id}/reservations/{id} |              | 예약 상세 정보 |
|                     | 예약취소요청   | 예약정보 상태 데이터 `PROCESSING`으로 변경 | PATCH  | /members/{id}/reservations/{id} |              |                |

## 관리자 예약

| IDX                | 기능명       | 설명                                 | Method | API Path           | Request Body | Response Body |
| ------------------ | ------------ | ------------------------------------ | ------ | ------------------ | ------------ | ------------- |
| Admin, Reservation | 예약내역조회 | 전체예약내역조회                     | GET    | /reservations      |              |               |
|                    | 예약취소처리 | 예약정보 상태 데이터 `CANCEL`로 변경 | PATCH  | /reservations/{id} |              |               |
|                    | 결제취소처리 | 부트페이를 활용한 결제취소처리       | POST   | /payments/cancel   | receiptId    | 취소 결과     |

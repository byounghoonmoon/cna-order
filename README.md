# cna-order
| 기능 | 이벤트 Payload |
|---|:---:|
| 관관리자가 병원 정보( 병원이름, 예약일, 가능인원수)를 등록한다. | {"eventType":"HospitalRegistered","timestamp":"20200901184726","id":1,"hospitalNm":"Samsung","chkDate":"20200913","pCnt":2100,"me":true} |
| 고객이 건강검진을 예약을 요청한다. (Sync)</bt>해당 병원의 검진가능 인원이 감소한다. (Sync)</br>예약 완료로 변경된다. (Sync)</br> 예약관리의 해당 내역의 상태가 등록된다. | 제일 아래와 같은 형태로 kafka 메시지를 찍어준다. |
| 고객이 건강검진 예약을 취소한다.</br>취소 시, 병원의 검진가능 인원이 증가한다. (Async)</br>예약관리의 해당 내역의 상태가 예약 취소로 변경된다. | 제일 아래와 같은 형태로 kafka 메시지를 찍어준다. |
| 관리자가 병원 정보를 삭제한다.</br>해당 병원에 예약한 예약자의 상태를 예약 강제 취소 변경한다.</br>예약관리의 해당 내역의 상태가 예약 강제 취소로 변경된다. | 제일 아래와 같은 형태로 kafka 메시지를 찍어준다. | 
| 건강검진 예약내역 상태를 조회한다.| 제일 아래와 같은 형태로 kafka 메시지를 찍어준다. |
| 사용자가 콘서트 예약내역 상태를 조회한다. | [{"id":1,"bookingId":6659,"concertId":1,"userId":1,"status":"BookingRequested"},</br> {"id":2,"bookingId":6660,"concertId":3,"userId":1,"status":"PaymentCanceled"}] |

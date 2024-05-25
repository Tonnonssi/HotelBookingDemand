##   변수 설명 

| 변수명                       | 자료형          | 변수 설명                                                                                           | values                          |
|-----------------------------|-----------------|-----------------------------------------------------------------------------------------------------|---------------------------------|
| index                       | int             | 119,390 obs.                                                                                       |                                 |
| hotel                       | chr(범주형)     | 호텔 종류                                                                                           | City Hotel / Resort Hotel       |
| is_canceled                 | bool, int       | 취소했는지 여부                                                                                     | 0 / 1                           |
| lead_time                   | int, 날짜       | 예약 날짜~호텔 도착 날짜 사이의 day                                                                  | 0~737                           |
| arrival_date_year           | int, 날짜       | 호텔 도착 연도                                                                                       | 2015~2017                       |
| arrival_date_month          | chr(범주형), 날짜 | 호텔 도착 월                                                                                        | January, …, December            |
| arrival_date_week_number    | int, 날짜       | 호텔 도착 주. n번째 주                                                                               | 1~53                            |
| arrival_date_day_of_month   | int, 날짜       | 호텔 도착 일                                                                                        | 1~31                            |
| stays_in_weekend_nights     | int, 날짜       | 주말 숙박 일수                                                                                       | 0~19                            |
| stays_in_week_nights        | int, 날짜       | 평일 숙박 일수                                                                                       | 0~50                            |
| adults                      | int             | 성인 인원 수                                                                                         | 0~55                            |
| children                    | int             | 아동/청소년 인원 수                                                                                  | 0~10                            |
| babies                      | int             | 유아 인원 수                                                                                         | 0~10                            |
| meal                        | chr(범주형)     | 식사 예약 종류                                                                                       | 5가지                           |
| country                     | chr(범주형)     | 호텔 위치 국가                                                                                       | 178가지                         |
| market_segment              | chr(범주형)     | 마켓 구분 (TA: Travel Agent, TO: Tour Operators)                                                     | 8가지                           |
| distribution_channel        | chr(범주형)     | 예약 타입 (TA: Travel Agent, TO: Tour Operators)                                                     | 5가지                           |
| is_repeated_guest           | bool, int       | 재방문 여부                                                                                         | 0 / 1                           |
| previous_cancellations      | int             | 이전에 예약을 취소한 횟수                                                                            | 0~26                            |
| previous_bookings_not_canceled | int         | 이전에 예약 후 취소하지 않은 횟수                                                                     | 0~72                            |
| reserved_room_type          | chr(범주형)     | 예약 객실 타입                                                                                       | A~G, L, P (10가지)              |
| assigned_room_type          | chr(범주형)     | 배정된 객실 타입                                                                                     | A~I, K, L, P (12가지)           |
| booking_changes             | int             | 예약 후 예약 변경 횟수                                                                               | 0~21                            |
| deposit_type                | chr(범주형)     | 디파짓(보증금) 타입                                                                                  | No Deposit / Non Refund / Refundable |
| agent                       | chr(범주형)     | 예약한 에이전트 ID                                                                                   | 334가지                         |
| company                     | chr(범주형)     | 예약한 회사 ID (호텔을 예약하거나 비용을 지불할 책임이 있는 회사)                                       | 353가지                         |
| days_in_waiting_list        | int             | 예약 확정 전까지 대기 명단에 있던 기간                                                                | 0~391                           |
| customer_type               | chr(범주형)     | 고객 유형                                                                                           | Contract / Group / Transient / Transient-Party |
| adr                         | num             | 평균 일일 숙박비 (객단가: 부킹 사이트에 따라 가격이 다르다.)                                           | -6.38~5400                      |
| required_car_parking_spaces | int             | 필요한 주차공간 개수                                                                                 | 0~8                             |
| total_of_special_requests   | int             | 특별 요청 횟수                                                                                       | 0~5                             |
| reservation_status          | chr(범주형)     | 마지막 예약 상태                                                                                    | Canceled / Check-Out / No-Show  |
| reservation_status_date     | chr(범주형), 날짜 | 마지막 예약 상태가 설정된 일자                                                                       | 2014년~2017년 yyyy-mm-dd        |

# EDA 결과

## 분석 방향

1. cancel에 대한 분석
2. 어린이, 유아 고객에 대한 분석
3. 평균 가격에 대한 분석

## 1. 취소된 건에 대한 전반적인 분석

### 01. 전체 데이터에서 취소 비율

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/083957a0-f2f0-431d-994b-9d5bb87b8acb)


취소율 : 0.3704163

### 02. **재방문 / 첫방문에 따른 과거 취소 빈도 수 차이**

- 첫 방문인 고객의 과거 취소 빈도 수
    
    ```r
    ##    1    2    3    6   11   14   19   24   25   26
    ## 5358   40   13    6    8   14   19   48   25   26
    
    >> weighted_sum = 8611
    ```
    
- 재방문인 고객의 과거 취소 빈도 수
    
    ```r
    ##   1   2   3   4   5   6  11  13  21 
    ## 693  76  52  31  19  16  27  12   1
    
    >> weighted_sum = 1790
    ```
    

첫 방문인 고객의 과거 취소 빈도 수가 많았다. 

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/0c8cad1e-5b3d-4b0d-a41c-2188b1996bc5)

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/a17f56bf-fee6-4ebe-823f-0484728d869b)


첫 방문 고객 중에 한 번 캔슬한 경우가 압도적으로 많았다. 시각화에 있어 1이 outlier의 역할을 하기에, 1을 제외한 그래프를 그렸다. 그 결과 고빈도 캔슬 수는 첫 방문인 경우가 많고, 저빈도 캔슬 수는 재방문인 경우가 많았다.

### 03. 과거 취소와 현재 취소가 관련이 있을 것이다.

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/dd34560b-7ab9-42d6-9ae1-89d771802936)

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/312e3414-22cc-4909-a3d0-f7e5e0d15cef)


과거에도 현재에도 취소를 한 적 없는 사람이 가장 많았다. 현재 취소를 기준으로 생각해보면 취소 전적이 있는 사람이 없는 사람보다 취소 빈도가 많았다. 하지만 전체 빈도를 기준으로만 생각한다면, 과거 취소 전적이 있는 사람들은 균등하게 현재 취소 O/X에 분포되어 있다. 

### 04. 예약과 방문 사이의 시간차와 취소가 관련이 있을 것이다.

- **전체 케이스**

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/5736b738-5c1d-48fe-9e74-9b9c13197b0c)


방문한 손님은 직전에 예약하는 경우가 많다. 

대략 1달보다 빨리 예약한 경우 취소하는 건수가 더 많다.

- **첫 방문 손님일 경우**

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/2fe66830-1d5a-4299-b9fc-113de7445065)


첫 손님인 경우, 방문한 손님보다 취소한 손님이 더 방문과 예약 사이의 기간이 길다.

- **재방문 손님일 경우,**

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/97fba0d5-804d-414e-865e-a4c7c0d7f490)


재방문 손님의 경우도 첫 방문과 동일하게 직전 예약이 가장 많다. 

### 05. 예약 변경 횟수와 취소는 관계가 있을 것이다.

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/de621c98-6213-4694-b51c-1f91f0f68c91)


대부분 5회 이내로 예약을 변경하며, 취소하지 않은 사람이 예약을 바꾼 경우가 더 많다.

## 2. 방

### 01. 배정받은 방과 예약한 방

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/03a39e5b-54ee-479b-8a6f-5d0e9a18c9cb)


I,K 타입은 예약한 케이스는 없는데 배정받은 경우만 있으며, A-H 방까지만 I,K 타입 방을 배정받는다. 대부분 자기가 예약한 방을 갖는다. L 타입이 유독 예약한 것과 다른 방을 배정받는 경우가 많다.

### 02. 예약한 방 별 취소비율

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/faa100ad-d945-4854-9b13-7a469d9f1822)


P 타입 방을 예약한 사람이 전부 예약을 취소했다.

### 03. 각 hotel의 월별 예약된 room type

<City Hotel>

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/a8618d07-99d9-467d-b243-8ac6493e6596)


<Resort Hotel>

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/61b00848-ae30-4af4-981a-8d5cf9d68476)


- 두 호텔 모두 room A의 개수가 아주 많다.
- City Hotel은 room A 다음으로 D의 개수가 많다. A, D 둘 다 월별 차이가 많이 나는 편이지만, 전체 예약 건수와 비례하는 듯하다.
- Resort Hotel은 전체 예약 건수의 절반 정도가 A, 그 뒤로 D, E의 예약이 많다. room A는 월별 예약건수의 차이가 거의 없지만, D, E는 예약이 몰리는 7, 8월에 확연히 늘어난다.

## 3. babies(아기의 수) 변수

### 01. babies 유무에 따른 meal type 선택 비율

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/23040cf5-2288-45ea-95a5-abb35fc0bc65)


아이가 있는 경우 HB의 선택 비율이 아이가 없는 경우보다 더 높고, 반대로 SC의 비율이 더 낮았다.

- HB = Half Board (Breakfast & Dinner), SC = Self Catering

### 02. babies 유무에 따른 total_of_special_requests(특별 요구사항)의 수

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/8e288740-8154-40fd-957c-5e1a99ae2349)


아이가 있는 집단의 전체 특별 요구사항이 아이가 없는 집단보다 많은 편임을 알 수 있다.

## 4. 방의 평균 가격(adr) 변수

### 01. adr 변수 관찰

`Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
  -6.38   69.29   94.58  101.83  126.00 5400.00`  

- 음수인 값과 너무 큰 값은 outlier. 제거 후 관찰

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/593165f9-f712-43ce-88ca-88dc262bcdd8)


- 대부분의 값이 100 근처에 몰려있다

### 02. hotel, room type에 따른 adr

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/0dd9a458-d679-47b4-b579-80b13f60f296)


- hotel과 room type에 따라 평균 가격에 차이가 있다.
- 이후 다른 변수와 adr의 관계를 분석할 때, hotel, room type별로 가격의 차이가 있다는 것을 고려해서 분석할 필요가 있다.

### 03. 각 hotel의 월별 adr

<City Hotel>

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/a3aa1a6e-bb30-4bdf-8fa5-056dab2fb029)


<Resort Hotel>

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/76470691-dcc9-4cd3-ae60-f006553428c8)


- 두 호텔 모두 여름에 평균 가격이 오르고 겨울에 떨어진다. City Hotel은 월별 차이가 크지 않지만, Resort Hotel은 5~8월 평균 가격이 다른 달보다 월등히 높다. 특히 7, 8월에 평균가격이 크게 올랐다가 9월에 급격하게 떨어진다.

### 04. hotel, room type에 따른 lead time과 adr의 관계

<City Hotel>

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/2e331340-f267-4f78-acf3-31c8f7e1cf7b)


<Resort Hotel>

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/0fa972a3-df5a-467f-b919-5c8b5200559e)


- room type별로 대체로 비슷한 분포를 띈다. 분명한 상관관계가 보이지는 않지만, 숙박 날짜 직전에 예약한 경우 adr의 분포가 더 넓게 퍼져있는 경향이 있고, 숙박 날짜보다 훨씬 일찍 예약한 경우에 가격이 더 낮은 경향이 보인다. 이러한 경향은 City Hotel 보다 Resort Hotel에서 더 뚜렷하게 보인다.
- Resort Hotel의 room D에서 lead time이 약 200 이상인 경우에 adr이 급격하게 낮아지는 경향이 보인다.

### 05. 포르투갈과 다른 국가에서 온 사람들의 adr 비교

<포르투갈>

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/856b2195-de79-4145-9e29-875ea5897f16)


<다른 국가>

![image](https://github.com/Tonnonssi/HotelBookingDemand/assets/126959470/a2238e4a-ff73-40d5-9153-07f0fd80ec57)


- 해당 데이터셋의 호텔이 포르투갈에 위치한 호텔이기 때문에 현지 여행객과 다른 국가에서 온 여행객의 평균 가격을 비교했다.
- 포르투갈 현지 여행객의 adr이 다른 국가에서 온 여행객의 adr에 비해 약간 낮은 편이다.

# EDA 결과

## 분석 방향

1. cancel에 대한 분석
2. 어린이, 유아 고객에 대한 분석
3. 평균 가격에 대한 분석

## 1. 취소된 건에 대한 전반적인 분석

### 01. 전체 데이터에서 취소 비율

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/63a5041f-bf96-4637-9e62-9b4c3cf1cfb9/Untitled.png)

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

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/a12a2ba9-c5ee-41ad-be2c-2674976b7411/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/bd84d377-d3da-4803-a8a7-2898a22ab15e/Untitled.png)

첫 방문 고객 중에 한 번 캔슬한 경우가 압도적으로 많았다. 시각화에 있어 1이 outlier의 역할을 하기에, 1을 제외한 그래프를 그렸다. 그 결과 고빈도 캔슬 수는 첫 방문인 경우가 많고, 저빈도 캔슬 수는 재방문인 경우가 많았다.

### 03. 과거 취소와 현재 취소가 관련이 있을 것이다.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/aac12ba3-791f-433f-96f6-554ab8751dfa/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/bba8eea4-399d-4af0-a77e-5a4030308af6/Untitled.png)

과거에도 현재에도 취소를 한 적 없는 사람이 가장 많았다. 현재 취소를 기준으로 생각해보면 취소 전적이 있는 사람이 없는 사람보다 취소 빈도가 많았다. 하지만 전체 빈도를 기준으로만 생각한다면, 과거 취소 전적이 있는 사람들은 균등하게 현재 취소 O/X에 분포되어 있다. 

### 04. 예약과 방문 사이의 시간차와 취소가 관련이 있을 것이다.

- **전체 케이스**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/2b3609d3-4302-4959-95f2-5214ee0f208c/Untitled.png)

방문한 손님은 직전에 예약하는 경우가 많다. 

대략 1달보다 빨리 예약한 경우 취소하는 건수가 더 많다.

- **첫 방문 손님일 경우**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/106079d7-44f2-4b43-b0ea-4b558ceaef35/Untitled.png)

첫 손님인 경우, 방문한 손님보다 취소한 손님이 더 방문과 예약 사이의 기간이 길다.

- **재방문 손님일 경우,**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/508cd1ec-7013-4a17-b6ac-f34536c0c2fb/Untitled.png)

재방문 손님의 경우도 첫 방문과 동일하게 직전 예약이 가장 많다. 

### 05. 예약 변경 횟수와 취소는 관계가 있을 것이다.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/1c9bd669-d102-4982-9e29-efff1931b177/Untitled.png)

대부분 5회 이내로 예약을 변경하며, 취소하지 않은 사람이 예약을 바꾼 경우가 더 많다.

## 2. 방

### 01. 배정받은 방과 예약한 방

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/b9cf4b75-b82b-4a05-888a-60df67f85dee/Untitled.png)

I,K 타입은 예약한 케이스는 없는데 배정받은 경우만 있으며, A-H 방까지만 I,K 타입 방을 배정받는다. 대부분 자기가 예약한 방을 갖는다. L 타입이 유독 예약한 것과 다른 방을 배정받는 경우가 많다.

### 02. 예약한 방 별 취소비율

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/021375af-49bd-4a50-b5ec-db791dda208d/Untitled.png)

P 타입 방을 예약한 사람이 전부 예약을 취소했다.

### 03. 각 hotel의 월별 예약된 room type

<City Hotel>

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/e1ae42b8-4303-4844-88b2-d6a9641d0583/Untitled.png)

<Resort Hotel>

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/200cc227-079a-4abf-9ce8-769c6a7306f4/Untitled.png)

- 두 호텔 모두 room A의 개수가 아주 많다.
- City Hotel은 room A 다음으로 D의 개수가 많다. A, D 둘 다 월별 차이가 많이 나는 편이지만, 전체 예약 건수와 비례하는 듯하다.
- Resort Hotel은 전체 예약 건수의 절반 정도가 A, 그 뒤로 D, E의 예약이 많다. room A는 월별 예약건수의 차이가 거의 없지만, D, E는 예약이 몰리는 7, 8월에 확연히 늘어난다.

## 3. babies(아기의 수) 변수

### 01. babies 유무에 따른 meal type 선택 비율

![스크린샷 2024-05-22 오후 2.10.51.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/6d31e5ae-835a-4292-9cde-90c6757ad0f5/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-05-22_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_2.10.51.png)

아이가 있는 경우 HB의 선택 비율이 아이가 없는 경우보다 더 높고, 반대로 SC의 비율이 더 낮았다.

- HB = Half Board (Breakfast & Dinner), SC = Self Catering

### 02. babies 유무에 따른 total_of_special_requests(특별 요구사항)의 수

![스크린샷 2024-05-22 오후 2.14.31.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/283f650e-2f2f-4dd5-be7f-7f3fcc6d5381/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-05-22_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_2.14.31.png)

아이가 있는 집단의 전체 특별 요구사항이 아이가 없는 집단보다 많은 편임을 알 수 있다.

## 4. 방의 평균 가격(adr) 변수

### 01. adr 변수 관찰

`Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
  -6.38   69.29   94.58  101.83  126.00 5400.00`  

- 음수인 값과 너무 큰 값은 outlier. 제거 후 관찰

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/a845df1f-badc-4e3b-add8-29067ca3d6e7/Untitled.png)

- 대부분의 값이 100 근처에 몰려있다

### 02. hotel, room type에 따른 adr

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/bf756ea9-bac7-4ed8-9d73-0bad7708bdba/Untitled.png)

- hotel과 room type에 따라 평균 가격에 차이가 있다.
- 이후 다른 변수와 adr의 관계를 분석할 때, hotel, room type별로 가격의 차이가 있다는 것을 고려해서 분석할 필요가 있다.

### 03. 각 hotel의 월별 adr

<City Hotel>

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/ea1cf340-1853-4c8a-96fa-625f78df68cf/Untitled.png)

<Resort Hotel>

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/78b921d1-0f68-48cb-b8d3-2b0db2c32d74/Untitled.png)

- 두 호텔 모두 여름에 평균 가격이 오르고 겨울에 떨어진다. City Hotel은 월별 차이가 크지 않지만, Resort Hotel은 5~8월 평균 가격이 다른 달보다 월등히 높다. 특히 7, 8월에 평균가격이 크게 올랐다가 9월에 급격하게 떨어진다.

### 04. hotel, room type에 따른 lead time과 adr의 관계

<City Hotel>

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/1de8abf7-900d-40a5-b8ab-ef5292c06e86/Untitled.png)

<Resort Hotel>

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/69710425-be94-4beb-9b0b-17befdf21e14/Untitled.png)

- room type별로 대체로 비슷한 분포를 띈다. 분명한 상관관계가 보이지는 않지만, 숙박 날짜 직전에 예약한 경우 adr의 분포가 더 넓게 퍼져있는 경향이 있고, 숙박 날짜보다 훨씬 일찍 예약한 경우에 가격이 더 낮은 경향이 보인다. 이러한 경향은 City Hotel 보다 Resort Hotel에서 더 뚜렷하게 보인다.
- Resort Hotel의 room D에서 lead time이 약 200 이상인 경우에 adr이 급격하게 낮아지는 경향이 보인다.

### 05. 포르투갈과 다른 국가에서 온 사람들의 adr 비교

<포르투갈>

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/2737d95e-3954-4033-9be1-ebc1cff4b6c9/Untitled.png)

<다른 국가>

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/1bb94ec1-750b-43ee-be10-e0d27329a0df/08a7835a-a6db-4395-8a27-f34f80c5f918/Untitled.png)

- 해당 데이터셋의 호텔이 포르투갈에 위치한 호텔이기 때문에 현지 여행객과 다른 국가에서 온 여행객의 평균 가격을 비교했다.
- 포르투갈 현지 여행객의 adr이 다른 국가에서 온 여행객의 adr에 비해 약간 낮은 편이다.

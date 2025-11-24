# Ecommerce-sales-analysis
This project aims to track the monthly revenue and other relevant key performance indicators (KPIs) to monitor the financial stability of a Brazilian ecommerce sales platform. 

## 배경
<p align="center">
  <img src="https://github.com/Venusgalaxy1022/Ecommerce-sales-analysis/blob/main/imgs/olist_logo.png?raw=true" width="350" height="100">
</p>

본 프로젝트는 Brazilian E-Commerce 플랫폼 Olist의 온라인 쇼핑몰의 월별 매출 추이와 이를 구성하는 핵심 하위 지표를 분석하는 것을 목표로 한다. 이커머스 사업의 건전성을 판단하는 가장 기본적인 지표는 매출(Revenue)이나 단순 매출액만으로는 충분한 인사이트를 얻기 어렵기 때문에, 매출을 다시 세부 구성 요소로 분해해 보다 입체적으로 분석해보고자 한다. 본 프로젝트에서는 2017년 기준 Olist 데이터를 활용해 매출 및 하위 지표를 종합 분석하고,
이커머스 데이터 분석가 관점에서 비즈니스 인사이트를 도출한다.

## 활용 데이터

<p align="center">
  <img src="https://github.com/Venusgalaxy1022/Ecommerce-sales-analysis/blob/main/imgs/erd.png?raw=true" width="350">
</p>

### Brazilian E-Commerce Public Dataset by Olist
- 약 100,000건의 실제 브라질 이커머스 주문 데이터
- 주문, 고객, 제품, 주문상품 외에도 배송, 리뷰 등 다양한 정보 포함
- 분석 기간: 2016–2018년
- 개인정보 익명화 및 샘플링 완료

### 본 프로젝트에서 활용한 테이블
- olist_products
- olist_orders
- olist_order_items
- olist_customers


## 활용 툴
- Google BigQuery: 테이블 결합 및 지표 계산
- Tableau: 시각화 및 대시보드 제작
- Python: 전처리/추가 분석
- Google Spreadsheet: Tableau 연결

## 분석 쿼리

### Bigquery를 활용하여 데이터 가공
![BigQuery](https://github.com/Venusgalaxy1022/Ecommerce-sales-analysis/blob/main/imgs/bigquery_sql.png?raw=true)
- https://console.cloud.google.com/bigquery?invt=AbuIKQ&project=zerobase-olist-475502&supportedpurview=project&ws=!1m5!1m4!4m3!1szerobase-olist-475502!2solist!3solist_order_items


## 분석 결과

1. 2017년 월별 매출 분석

2017년 한 해 동안의 매출의 추이는 아래와 같고, 한 해동안 지속적으로 매출액이 향상되는 성장세를 보이고 있다. 특히 3월, 5월, 11월에 상대적으로 큰 매출액을 달성하고 있고, 이에 따라 익월 기준 전월 대비 매출액이 감소하는 패턴을 보인다. 

그러나, 해당 월의 매출액이 과도하게 이상하게 추산된 것은 아니고 모종의 합리적인 이유로 매출이 증가한 것임을 알 수 있다. 왜냐하면, 관련된 월의 경우 모두 이상치 판단 기준 범위 내에 있기 때문이다 (±2.5 표준편차 적용). 

더불어, 상세 분석 결과 해당 기간 매출 증대는 가장 직접적으로 이용 고객수 증가에 따른 주문 수 증가로 확인된다. 서비스의 성숙도가 높아지면서 고객 유치 및 활성 고객 증대에 효과가 나타난 것으로 보인다. 

![월별매출추이](https://github.com/Venusgalaxy1022/Ecommerce-sales-analysis/blob/main/imgs/월별매출추이.png?raw=true)


2. 상세 지표 분석

아래는 같은 해 매출액, 주문수, 주문상품수의 월별 추이를 보여주는 대시보드이다. 세가지 지표 모두 동일한 패턴을 보인다. 연말로 갈 수록 상승하는 패턴을 보여준다. 

![세부지표추이](https://github.com/Venusgalaxy1022/Ecommerce-sales-analysis/blob/main/imgs/세부지표추이.png?raw=true)

## 결론

- 월별 매출, 주문수, 상품수가 대체적으로 상승하는 패턴을 보인다. 
- 특히 3월, 5월, 11월에 상승 폭이 크며, 공통적으로 매출이 높아지는 원인이 무엇인지 확인해 볼 필요가 있다. 이러한 트렌드가 연도, 취급범위(종합몰, 전문몰), 운영형태(오프라인, 온라인, 복합), 취급상품군, 플랫폼/자체 쇼핑몰 상관없이 동일하게 유지되는지도 분석해보면 좋을 것 같다. 
- 11월에는 특별히 매출이 높아지므로, 이 때 매출을 더욱 확대할 수 있는 이벤트를 강구하면 좋을 것 같다. 
- 월별 매출 상승의 트렌드의 주요 드라이버는 고객수로 볼 수 있다. 그러나, 분석 결과 딱히 한 명의 고객의 재구매 빈도는 크지 않은 편이다. 따라서, 새로운 고객 확보와 더불어 기존 고객의 재방문률 및 재구매 빈도를 높이기 위한 마케팅 방안을 마련할 필요가 있다. 


## 회고

1. 지표를 만드는 과정은 "접근할 수 있는 단위로 쪼개는" 과정과 같다. 즉, 심리학에서 조작적 정의를 설정하는 것과 비슷한 과정으로 특정 개념을 측정할 수 있는 방법이나 내용으로 정확하게 표현하는 것이다. 언제나 큰 그림을 볼 수 있는 지표를 먼저 구상하거나 보고, 그 다음에 세부적으로도 보는 습관을 길러보자.

이커머스 비즈니스 지표 (이커머스 지표라고는 하지만, 오프라인도 동일한 지표를 사용할 것으로 예상됨)

- 매출: 들어온 주문수 & 건당 주문 금액
- 주문 건수: 고객수 & 주문 빈도 (한 명이 반드시 한 번만 주문하는 건 아니니깐)
- 건당 주문 금액(평균 얼마정도 주문):판매품목 수 & 물품 평균 가격 

2. 이번 프로젝트는 가장 기본적인 매출 데이터를 분석하여 High Level 인사이트를 제시했다. 
현업에서는 이를 데이터로 검증 가능한 가설과 실행 가능한 전략으로 구체화 시켜서 실제 캠페인, 프로모션, 상품전략으로 이어간다. 데이터를 실제 액션으로 전환하는 실습을 많이 진행해보자. 

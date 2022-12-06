![image](https://user-images.githubusercontent.com/487999/79708354-29074a80-82fa-11ea-80df-0db3962fb453.png)

# 예제 - 음식배달

## 기능적 요구사항

1.고객이 메뉴를 선택하여 주문한다.

2.고객이 선택한 메뉴에 대해 결제한다.

3.주문이 되면 주문 내역이 입점상점주인에게 주문정보가 전달된다.

4.상점주는 주문을 수락하거나 거절할 수 있다.

5.상점주는 요리시작때와 완료 시점에 시스템에 상태를 입력한다.

6.고객은 아직 요리가 시작되지 않은 주문은 취소할 수 있다.

7.요리가 완료되면 고객의 지역 인근의 라이더들에 의해 배송건 조회가 가능하다.

8.라이터가 해당 요리를 pick한 후, 앱을 통해 통보한다.

9.고객이 주문상태를 중간중간 조회한다.

10.주문상태가 바뀔때 마다 카톡으로 알림을 보낸다.

11.고객이 요리를 배달 받으면 배송확인 버튼을 탭하여, 모든 거래가 완료된다.


추가사항
1. 고객은 결재 내역과 상태를 확인할 수 있다.

2. 라이더는 pick이 있는지 여부와 배달완료가 되었는지 확인한다.

## DDD 적용
![image](https://user-images.githubusercontent.com/118959734/205806811-d569d167-caee-4d7b-8c8d-4c07ad5e08de.png)


# 구현
## 체크포인트

### 1.Saga(Pub/Sub)
고객이 주문하고 결재가 처리되면 상점에 주문내역이 전달된다.
![image](https://user-images.githubusercontent.com/118959734/205808546-41d561a4-2ea1-41d5-96fc-b93516060759.png)

![image](https://user-images.githubusercontent.com/118959734/205808638-ee4d0c3f-0240-4e90-86dc-7529b76a757b.png)

![image](https://user-images.githubusercontent.com/118959734/205808796-f37da38d-4215-407d-b938-66174b950678.png)
![image](https://user-images.githubusercontent.com/118959734/205808844-a320ee59-cd0b-47be-afcb-738d1fa9de7c.png)



### 2.CQRS

### 3.Compensation/Correlation 

### 4.Request/Response  

### 5.Circuit Breaker  

### 6.Gateway/Ingress  







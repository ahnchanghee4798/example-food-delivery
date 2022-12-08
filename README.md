![79708354-29074a80-82fa-11ea-80df-0db3962fb453](https://user-images.githubusercontent.com/119610308/205784843-706ff400-2229-45a2-8828-ec81e10c6674.png)

서비스 시나리오
[이벤트스토밍]


   ![image](https://user-images.githubusercontent.com/119610308/206396835-12d9328e-a444-4c5d-a85c-774df056084b.png)

   
   
   
   기능적 요구사항
   
   1. 고객이 메뉴를 선택하여 주문 합니다.
   2. 고객이 선택한 메뉴에 대해 결제 합니다.
   3. 주문이 되면 주문 내역이 입점상점주인에게 주문정보가 전달된다.
   4. 상점주는 주문을 수락하거나 거절할 수 있다.
   5. 사점주는 요리시작때와 완료 시점에 시스템에 상태를 입력한다.
   6. 고객은 아직 요리가 시작되지 안은 주문은 취소할 수 있다.
   7. 요리가 완료되면 고객의 지역 인근의 라이더들에 의해 배송건 조회가 가능하다.
   8. 라이더가 해당 요리를 pick한 후, 앱을 통해 동보한다. 바운디드 콘텍스트
   9. 고객이 주문상태를 중간중간 조회한다. 팔로시
   10. 주문상태가 바뀔 때 마다 카톡으로 알림을 보낸다.
   11. 고객이 요리를 배달 받으면 배송확인 버튼을 탭하여, 모든 거래가 완료 된다.
   12. 상점주는 주문이 완료 되면 감사메시지를 고객에게 보내 줍니다 v
   13. 고객은 아직 요리가 시작되지 않은 주문은 변경할 수 있다 v
   
   
   
   체크포인트









1. Saga(Pub / Sub)  이벤트드리븐 테입 방식으로 녹아 있어야 하나. 디테일 하게 제출
   ![image](https://user-images.githubusercontent.com/119610308/205851112-63dcc89e-e642-4529-acee-71b8eb1faa88.png)
   ![image](https://user-images.githubusercontent.com/119610308/205850522-3ed0c50c-a01c-4881-a21c-33722fe22986.png)



   

2. CQRS  v
   커맨터 액션 수정 삭제 추가
   데이터 프로덕션  
   
        

	![image](https://user-images.githubusercontent.com/119610308/205808923-099a7142-3ecc-43fa-bef7-56f4d9390ed9.png)

	![image](https://user-images.githubusercontent.com/119610308/205808637-63621501-bda8-45e2-b1e7-698be6bc8355.png)


	
	
   
3. Compensation /Correlation
   제고 부족   / 키 버 톤과 같다 where 조건절
   
 ![image](https://user-images.githubusercontent.com/119610308/205835624-a163eebe-976b-4f53-8976-1140e4fbe4b7.png)
  
 ![image](https://user-images.githubusercontent.com/119610308/205835557-a16dd591-baf1-4bf5-9ecd-be3129f25964.png)

 


4. Request / Response
   동기 호출
   
   기존 주문이 되었을때 동기 통신
   사가를 이용해서 주문이 시작 해서 호출이 되고
   반드시 해야 할대 동기 호출 할수 있다.
   10개 시나리오에서 변경해서 제출
   
![image](https://user-images.githubusercontent.com/119610308/205857455-ec7c53da-b07e-40c1-94a8-be97bea70852.png)
   
![image](https://user-images.githubusercontent.com/119610308/205857237-8ea3b85b-02b9-46ed-b55c-6b9c8cb6714c.png)


   
   
   

5. Circuit Breaker
   rest로 호출했을때 기다리다가 서킷프래이커를 달자 임계치를 준다음 중지 시킨다.
   증적 자료가 있어야 한다.
   쿼리해서 워킹한다.
   
![image](https://user-images.githubusercontent.com/119610308/205837628-3882cf09-79e2-4457-9a96-0f04c4c1ea7d.png)
   
   
6. Gateway / Ingress
   포워딩하는 구조로 해야 한다. 온라인 교육에서 자동 생성
   1. 트래픽 라우팅 부문 신원 인가 부분 트래픽 메니져먼트 부문
      만들어 준것을 잘설명 한다.
	  
![image](https://user-images.githubusercontent.com/119610308/205837938-56897f6f-632a-41d9-9c7c-e1f3f1ee0e7b.png)





2개를 수정 하자 명시 해야 한다.

6개 시나리오가 디테일 하고 리프팅


이커머스 도메인으로 정리


1. 고객이 메뉴를 선택하여 주문 합니다.
2. 고객이 선택한 메뉴에 대해 결제 합니다.
3. 주문이 되면 주문 내역이 입점상점주인에게 주문정보가 전달된다.
4. 상점주는 주문을 수락하거나 거절할 수 있다.
5. 사점주는 요리시작때와 완료 시점에 시스템에 상태를 입력한다.
6. 고객은 아직 요리가 시작되지 안은 주문은 취소할 수 있다.
7. 요리가 완료되면 고객의 지역 인근의 라이더들에 의해 배송건 조회가 가능하다.
8. 라이더가 해당 요리를 pick한 후, 앱을 통해 동보한다. 바운디드 콘텍스트
9. 고객이 주문상태를 중간중간 조회한다. 팔로시
10. 주문상태가 바뀔 때 마다 카톡으로 알림을 보낸다.
11. 고객이 요리를 배달 받으면 배송확인 버튼을 탭하여, 모든 거래가 완료 된다.
12. 상점주는 주문이 완료 되면 감사메시지를 고객에게 보내 줍니다 [추가]
13. 고객은 아직 요리가 시작되지 않은 주문은 변경할 수 있다 [추가]


장애격리

1. 상점관리 기능이 수행되지 안더라도 주문은 365일 24시간 받을 수 있어야 한다. Async(event-driven), Eventual Consistency
2. 결제시슽메이 과중되면 사용자를 잠시동안 받지 안고 결제를 잠시후에 하도록 유도한다.
   Circuit breaker, fallback


성능 
1. 고객이 자주 상점관리에서 확인할 수 있는 배달상태를 주문시스템(프론트엔드)에서 확인할 수있어야 한다. CQRS
2. 배달상태가 바뀔때마다 카톡 등으로 알림을 줄 수 있어야 한다. Event driven


분석/설계 : http://labs.msaez.io


제약 사항

제시된 기능적 요구사항 중, 2개이상 수정(또는 주가) 하여 구현

결과 제출 :
> 수행 내용에 대한 결과과 리포팅을 구들 DOCS에 기재 (이름, URL 기재)
리포팅 템플릿 Url : [http](https://github.com/ahnchanghee4798/cmall/blob/main/README.md)

	  

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
   
   
   
  ![image](https://user-images.githubusercontent.com/119610308/206397293-f55fe4f5-17d1-4d24-934c-bf6c3310d050.png)










1. Saga(Pub / Sub)  이벤트드리븐 테입 방식으로 녹아 있어야 하나. 디테일 하게 제출
   ![image](https://user-images.githubusercontent.com/119610308/206405657-47eea5fa-1b56-4073-9ced-925e6d576b8c.png)
   ![image](https://user-images.githubusercontent.com/119610308/206405468-f6850fc5-caee-49e7-ab35-b03ea6b272c0.png)
   ![image](https://user-images.githubusercontent.com/119610308/206405517-fbc3f5d9-2d43-4c9f-b2b7-367a6bdc0d4f.png)





   

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
   ![image](https://user-images.githubusercontent.com/119610308/206431611-0e206747-fbe8-41a2-b5c7-f5cde214e3bc.png)

   ![image](https://user-images.githubusercontent.com/119610308/206429538-61d3b915-f7d3-4633-9264-c74c09fe60b9.png)

   ![image](https://user-images.githubusercontent.com/119610308/206429340-64b68bab-eef5-494c-a91c-a40603cf9a33.png)

   ![image](https://user-images.githubusercontent.com/119610308/206429205-6e64a46f-6ccb-4895-86ab-93b71c3c0860.png)
   ![image](https://user-images.githubusercontent.com/119610308/206429234-cdd660b0-65e4-4ada-9476-594f5add822d.png)

   
   
6. Gateway / Ingress
   포워딩하는 구조로 해야 한다. 온라인 교육에서 자동 생성
   1. 트래픽 라우팅 부문 신원 인가 부분 트래픽 메니져먼트 부문
      만들어 준것을 잘설명 한다.
      ![image](https://user-images.githubusercontent.com/119610308/206438699-6de786ec-12c9-4f4f-9f2e-5877b3120455.png)
      ![image](https://user-images.githubusercontent.com/119610308/206438755-02810d69-4765-4b8b-b4c4-90859edc2545.png)
     ![image](https://user-images.githubusercontent.com/119610308/206438786-41855f40-922c-48d5-ac55-2c7c0c4c9460.png)

	  



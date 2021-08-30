# 객체지향을 이용한 뱅킹 프로그램

> 과정명: 패스트 캠퍼스 KDT 핀테크 서비스 백엔드 개발 과정    
> 출제자: 원혜린(devwon)

## 프로젝트 설명!

자바로 객체 지향 프로그래밍을 배운 후 프로젝트에서 필요한 객체들을 설계하고 이를 구현합니다 . 기본 예금 계좌와 적금 계좌을 가진 뱅킹시스템을 구현하고 각 계좌의 성격에 대한 차이를 다형성을 이용하여 구현해 봅니다. 또한 입력값에 따른 계좌생성, 출금, 입금, 송금 기능을 호출하고 자바에서 제공되는 컬렉션 프레임워크들을 활용하여 뱅킹시스템을 관리할 수 있습니다. 이러한 프로젝트를 구현함으로써 실무에서 객체를 설계하는 방법, BigDecimal 데이터 타입을 이용하여 금액을 다루는 법, 객체 지향 프로그래밍의 장점을 활용하는 방법 그리고 여러 필요한 기능들을 구현하는 방법들을 익힐 수 있습니다.

## 프로젝트 과제 상세

### 계좌 클래스 설계와 구현
1. 계좌(일반 예금 계좌)에는 일반 예금 계좌와 적금 계좌가 있습니다. 계좌 클래스의 속성은 계좌종류(N: 예금계좌, S:적금계좌), 계좌번호, 소유자, 잔액, 활성화 여부 다섯 가지 입니다.
2. 적금 계좌 클래스는 일반 예금 계좌 클래스에서 상속을 받고 목표 금액 속성이 추가 됩니다.
3. 일반 예금 계좌 클래스의 각 속성에 getter/setter를 제공하고, 계좌 정보를 보여주는 getAccountInfo() 메서드를 구현합니다. 적금 계좌 클래스는 이 메서드를 재정의 하여 목표 금액 정보도 보여주도록 합니다.
4. 뱅크 클래스에서 호출할 출금, 입금 기본 메서드를 생성합니다.

### 뱅크 클래스 설계와 구현
5. 계좌 클래스에서 구현한 기본 클래스를 이용하여 계좌생성, 출금, 입금, 송금 메서드를 구현합니다. 메서드 내부적으로 입력값을 받는 액션이 있습니다.
6. 적금 계좌는 적금 계좌는 잔액이 목표 금액(%s원) 이상이어야 출금 가능하도록 상속받은 출금 메서드를 조금 다르게 구현해줍니다.


### 인터페이스 설계와 구현
7. 일반 예금 계좌와 적금 계좌의 이자율 정책은 다릅니다. (여기서의 이자 계산은 잔액의 x%를 추가로 제공해주는 것으로 한정합니다. 현실세계의 포인트 개념과 비슷합니다.) 일반 예금 계좌인 경우 1000만원 이상은 이자율이 50%, 500만원 이상은 7%, 100만원 이상은 4%, 1만원 이상은 2%, 그 외에는 1% 이자를 제공해줍니다. 적금 계좌의 경우 100만원 이상은 이자율이 50%, 그 외에는 1% 이자를 제공해줍니다.
8. 각 할인 정책을 구현하기 위해 InterestCalculator 인터페이스에 계좌 잔액에 대한 이자금액을 반환하는 메서드(BigDecimal getInterest(balance))를 선언하고, 이를 구현한 일반 예금 계좌 이자 계산 정책과 적금 계좌에 대한 이자 계산 정책 클래스를 만듭니다.



### 계좌 관리를 위한 컬렉션 프레임 워크 사용하기
9. 모든 계좌를 관리하기 위한 중앙은행 클래스를 만듭니다. 계좌를 배열에 관리하기 위해 ArrayList를 활용합니다.
10. 계좌별 이자 정책을 관리하기 위해 HashMap을 활용하고, key에 category, value에 각 category의 InterestCalculator 인스턴스 를 담습니다.

## 마치며..
제가 과제를 제출하면서 정한 요구사항들은 한정적이고 이외에도 구현해보시면서 자유롭게 요구사항 이외의 기능들이나 예외 처리등을 구현해보시는걸 추천드립니다. 예를 들어 커스텀 에러를 만들어보시거나 모임통장 기능등 요구사항 이외에는 자유롭게 구현하셔도 좋습니다. 저도 과제 제출은 처음이라 부족한 점이 많으니 샘플 코드에서 잘못된 부분이 있다면 자유롭게 고쳐주세요.

그럼 즐거운 과제되시길 바랍니다:)

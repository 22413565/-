# 1. Conceptualization

Wireless Table Order (WT Order)

<img width="1536" height="1024" alt="logo" src="https://github.com/user-attachments/assets/475da597-6514-4827-8c06-67e60cd3f5ab" />
![logo](https://github.com/user-attachments/assets/475da597-6514-4827-8c06-67e60cd3f5ab)

Student No  
22413565  

Name  
이창민  

E-Mail  
pect5511@naver.com  

[ Revision history ]

Revision date  
Version #  
Description  
Author  

2026.03.23  
1.00  
First draft  

= Contents =

1. Business purpose ..................................................................................

2. System context diagram .......................................................................

3. Use case list .........................................................................................

4. Concept of operation ............................................................................ 

5. Problem statement ................................................................................

6. Glossary .................................................................................................

7. References .................................................................................................

# 1. Business purpose

WTOrder는 음식점에서 사용되는 테이블 오더 시스템의 개념을 기반으로, 저비용 구조와 사용자 친화적 인터페이스를 통해 자영업자의 부담을 줄이고 모든 연령층이 쉽게 사용할 수 있도록 설계된 무선 주문 시스템이다.

테이블 오더 시스템은 고객이 직접 메뉴를 확인하고 주문할 수 있도록 하여 주문 과정을 자동화하는 시스템으로, 주문 정확도를 향상시키고 인건비 절감 효과를 제공한다. 주요 기능으로는 메뉴 조회, 주문 추가 및 수정, 주문 전송, 주문 상태 확인 등이 있다.

그러나 기존 시스템은 초기 설치 비용과 지속적인 수수료, 유지비용이 발생하여 경기 침체 상황에서 자영업자에게 경제적 부담으로 작용하고 있다. 특히 매출 감소와 고정 비용 증가로 인해 효율적인 운영이 어려운 상황이 지속되고 있다.

이에 WTOrder는 저비용 환경에서도 구축 가능한 구조를 기반으로 불필요한 비용 요소를 최소화하고, 오픈 환경에서도 활용 가능한 시스템을 지향한다. 또한, 고령 사용자 및 디지털 기기 사용이 익숙하지 않은 이용자도 쉽게 접근할 수 있도록 직관적이고 단순한 사용자 인터페이스를 제공하는 것을 목표로 한다.

이를 통해 WTOrder는 기존 테이블 오더 시스템 대비 경제성과 접근성을 동시에 개선한 대안 시스템으로서의 가치를 제공하고자 한다.

# 2. System context diagram

<img width="1536" height="1024" alt="diagram" src="https://github.com/user-attachments/assets/25ecf5b9-977d-4bca-9f35-bf0997bb595e" />
![diagram](https://github.com/user-attachments/assets/25ecf5b9-977d-4bca-9f35-bf0997bb595e)


# 3. Use case list

1) View Menu

Actor  
Customer  

Description  
고객이 메뉴 목록을 조회하고 사진 및 설명을 확인한다.

2) Add Order

Actor  
Customer  

Description  
고객이 원하는 메뉴를 선택하여 주문 목록에 추가한다.

3) Confirm Order

Actor  
Customer  

Description  
고객이 주문한 메뉴를 최종 확인할 수 있도록 한다.

4) Call Staff

Actor  
Customer  

Description  
고객이 직원을 호출하여 추가 요청을 전달한다.

5) Receive Order

Actor  
Kitchen  

Description  
주방이 시스템으로부터 고객 주문을 전달받는다.

6) Manage Menu

Actor  
Store  

Description  
관리자가 메뉴를 추가, 수정, 삭제한다.

7) Upload Photo

Actor  
Store  

Description  
관리자가 메뉴 사진을 등록하거나 수정한다.

8) Edit Description

Actor  
Store  

Description  
관리자가 메뉴 설명을 작성 및 수정한다.

9) Set Price

Actor  
Store  

Description  
관리자가 메뉴 가격을 설정하거나 변경한다.

10) Control Sold-out

Actor  
Store  

Description  
관리자가 메뉴 품절 여부를 설정 및 해제한다.

11) Monitor Orders

Actor  
Store  

Description  
관리자가 전체 주문 현황을 확인한다.

12) Process Order

Actor  
WTOrder System  

Description  
시스템이 고객 주문을 처리하고 주방으로 전달한다.

13) Manage Data

Actor  
WTOrder System  

Description  
시스템이 데이터베이스와 연동하여 정보를 저장 및 조회한다.

14) Store Menu Data

Actor  
Database  

Description  
메뉴 관련 정보를 저장한다.

15) Store Order Data

Actor  
Database  

Description  
주문 데이터를 저장한다.

16) Update Data

Actor  
Database  

Description  
주문 상태 및 정보를 업데이트한다.

17) Manage Store Information

Actor  
Admin  

Description  
본사가 여러 매장의 기본 정보와 운영 정보를 관리한다.

18) Monitor Store Data

Actor  
Admin  

Description  
본사가 각 매장의 운영 현황과 데이터를 통합적으로 확인한다.

# 4. Concept of operation

1) View Menu

Purpose  
고객이 주문 가능한 메뉴 정보를 확인할 수 있도록 한다.

Approach  
고객이 테이블 오더 시스템을 실행하면 시스템이 데이터베이스에서 메뉴 정보(이름, 가격, 사진, 설명)를 불러와 화면에 표시한다.

Dynamics  
고객이 시스템에 접속하여 메뉴를 탐색할 경우

Goals  
메뉴 조회 기능을 구현한다.

2) Add Order

Purpose  
고객이 원하는 메뉴를 주문 목록에 추가할 수 있도록 한다.

Approach  
고객이 메뉴를 선택하고 수량을 지정하면 시스템이 해당 항목을 주문 목록에 임시 저장한다.

Dynamics  
고객이 메뉴를 선택하고 주문 목록에 담을 경우

Goals  
메뉴 선택 및 주문 추가 기능을 구현한다.

3) Confirm Order

Purpose  
고객이 선택한 메뉴를 최종 주문으로 확인할 수 있도록 한다.

Approach  
고객이 주문 목록 화면에서 선택한 메뉴와 수량, 총 금액을 확인한다.

Dynamics  
고객이 주문을 완료한 경우

Goals  
주문내용 확인 기능을 구현한다.

4) Call Staff

Purpose  
고객이 직원에게 추가 요청을 전달할 수 있도록 한다.

Approach  
고객이 직원 호출 버튼을 누르면 시스템이 해당 요청을 카운터의 메인 화면에 전달한다.

Dynamics  
고객이 도움이 필요하여 직원을 호출할 경우

Goals  
직원 호출 기능을 구현한다.

5) Receive Order

Purpose  
주방이 고객의 주문 정보를 전달받을 수 있도록 한다.

Approach  
고객이 주문을 확정하면 시스템이 주문 내역을 주방에 전송한다.

Dynamics  
새로운 주문이 발생할 경우

Goals  
주문 전달 기능을 구현한다.

6) Manage Menu

Purpose  
관리자가 메뉴를 추가, 수정, 삭제할 수 있도록 한다.

Approach  
관리자가 관리 화면에서 메뉴 정보를 입력하거나 수정 또는 삭제하면 시스템이 데이터베이스를 갱신한다.

Dynamics  
관리자가 메뉴 구성을 변경할 경우

Goals  
메뉴 관리 기능을 구현한다.

7) Upload Photo

Purpose  
관리자가 메뉴 사진을 등록하거나 변경할 수 있도록 한다

Approach  
관리자가 이미지 파일을 업로드하면 시스템이 해당 사진을 메뉴 정보와 연결하여 저장한다.

Dynamics  
관리자가 메뉴 이미지를 등록 또는 수정할 경우

Goals  
메뉴 사진 등록 기능을 구현한다.

8) Edit Description

Purpose  
관리자가 메뉴 설명을 작성하거나 수정할 수 있도록 한다.

Approach  
관리자가 설명 내용을 입력하면 시스템이 이를 메뉴 데이터와 함께 저장한다.

Dynamics  
관리자가 메뉴 설명을 변경할 경우

Goals  
메뉴 설명 관리 기능을 구현한다.

9) Set Price

Purpose  
관리자가 메뉴 가격을 설정하거나 수정할 수 있도록 한다.

Approach  
관리자가 가격 정보를 입력하면 시스템이 데이터베이스에 반영하고 고객 화면에 최신 가격을 표시한다.

Dynamics  
관리자가 가격을 변경할 경우

Goals  
가격 설정 기능을 구현한다.

10) Control Sold-out

Purpose  
관리자가 품절 여부를 설정하여 주문 불가 상태를 반영할 수 있도록 한다.

Approach  
관리자가 품절 처리 버튼을 누르면 시스템이 해당 메뉴를 주문 불가 상태로 전환하고 고객 화면에 표시한다.

Dynamics  
재고 부족 등으로 특정 메뉴를 판매할 수 없을 경우

Goals  
품절 관리 기능을 구현한다.

11) Monitor Orders

Purpose  
관리자가 전체 주문 현황을 확인할 수 있도록 한다

Approach  
관리자 화면에서 시스템이 현재 접수된 주문과 처리 현황을 조회하여 표시한다.

Dynamics  
관리자가 매장 운영 상황을 모니터링할 경우

Goals  
주문 현황 조회 기능을 구현한다.

12) Process Order

Purpose  
시스템이 고객 주문을 정상적으로 처리하고 관련 구성요소에 전달할 수 있도록 한다.

Approach  
고객 주문이 접수되면 시스템이 주문 데이터를 검증하고 저장한 뒤 주방 및 관리자 화면에 반영한다.

Dynamics  
주문이 발생할 경우

Goals  
주문 처리 기능을 구현한다.

13) Manage Data

Purpose  
시스템이 메뉴, 주문, 사용자 데이터를 저장 및 조회할 수 있도록 한다.

Approach  
시스템이 각 기능 수행 시 데이터베이스와 연동하여 필요한 데이터를 저장, 수정, 조회한다.

Dynamics  
시스템 전반에서 데이터 처리가 필요한 경우

Goals  
데이터 관리 기능을 구현한다.

14) Store Menu Data

Purpose  
메뉴 정보를 안정적으로 저장할 수 있도록 한다.

Approach  
관리자가 입력한 메뉴명, 가격, 설명, 사진 정보를 데이터베이스에 저장한다.

Dynamics  
메뉴 정보가 등록 또는 수정될 경우

Goals  
메뉴 데이터 저장 기능을 구현한다.

15) Store Order Data

Purpose  
주문 정보를 저장하여 이후 처리와 조회가 가능하도록 한다.

Approach  
고객 주문이 확정되면 주문 번호, 주문 항목, 수량 등의 정보를 데이터베이스에 저장한다.

Dynamics  
주문이 완료될 경우

Goals  
주문 데이터 저장 기능을 구현한다.

16) Update Data

Purpose  
기존 데이터를 수정하여 최신 상태를 유지할 수 있도록 한다.

Approach  
주문, 메뉴, 사용자 정보가 변경되면 데이터베이스에서 해당 항목을 찾아 갱신한다.

Dynamics  
데이터 변경이 발생할 경우

Goals  
데이터 업데이트 기능을 구현한다.

17) Monitor Store Data

Purpose  
관리자가 여러 매장의 운영 데이터를 통합적으로 확인할 수 있도록 한다.

Approach  
관리자가 관리자 시스템에 접속하여 매장별 주문 현황, 매출 정보, 운영 상태 등을 조회 요청하면 시스템이 데이터베이스에서 해당 정보를 불러와 화면에 표시한다.

Dynamics  
관리자가 전체 매장 운영 상황을 모니터링하려는 경우

Goals  
매장 운영 데이터 조회 및 모니터링 기능을 구현한다.

18) Manage Store Information

Purpose  
관리자가 매장의 기본 정보 및 운영 정보를 관리할 수 있도록 한다.

Approach  
관리자가 매장 정보(매장명, 위치, 운영 시간 등)를 입력하거나 수정하면 시스템이 해당 정보를 데이터베이스에 저장 및 업데이트한다.

Dynamics  
매장 정보의 등록, 수정, 삭제가 필요한 경우

Goals  
매장 정보 관리 기능을 구현한다.

# 5. Problem statement

Overview)

WTOrder System은 매장에서 사용하는 테이블 오더 기반의 주문 관리 시스템으로,
고객(Customer), 주방(Kitchen), 매장(Store), 관리자(Admin) 간의 주문 및 데이터 흐름을 통합적으로 관리하는 시스템이다. 고객은 테이블에 설치된 디바이스를 통해 메뉴를 조회하고 주문을 생성할 수 있으며, 주문 정보는 시스템을 통해 주방으로 전달되어 조리가 진행된다. 매장은 메뉴 관리 및 주문 현황을 확인할 수 있고, 관리자는 여러 매장의 운영 데이터를 통합적으로 관리할 수 있다. 또한, 시스템은 데이터베이스와 연동하여 메뉴 정보, 주문 정보, 사용자 정보를 저장하고 실시간으로 처리한다. WTOrder System을 개발함에 있어 다음과 같은 문제점과 기술적 어려움을 고려해야 한다.

① 주문 처리 지연 문제  
동시에 많은 고객이 주문할 경우 시스템 부하로 인해 주문 처리 속도가 느려질 수 있다.  
이는 사용자 경험 저하 및 매장 운영 효율성 감소로 이어질 수 있다.

② 데이터 일관성 문제  
고객 주문, 매장 메뉴, 주방 처리 상태가 동시에 변경되기 때문에 데이터 불일치가 발생할 가능성이 있다.  
예를 들어, 품절된 메뉴가 주문되는 상황이 발생할 수 있다.

③ 실시간 정보 동기화 문제  
고객, 매장(Store), 주방(Kitchen), 관리자(Admin)가 동일한 데이터를 공유해야 하기 때문에  
실시간 상태 업데이트가 원활하지 않으면 혼선이 발생할 수 있다.

④ 네트워크 의존성 문제  
테이블 오더 시스템은 네트워크 기반으로 동작하기 때문에 인터넷 연결이 불안정할 경우  
주문 처리, 데이터 전송, 화면 갱신 등에 문제가 발생할 수 있다.

⑤ 사용자 인터페이스(UI) 접근성 문제  
다양한 연령층(특히 고령 사용자)이 사용할 수 있도록 직관적이고 단순한 UI 설계가 필요하다.  
복잡한 UI는 사용 오류를 유발할 수 있다.

⑥ 보안 및 개인정보 보호 문제  
사용자 정보 및 주문 데이터가 저장되므로 데이터 유출 및 무단 접근을 방지하기 위한 보안 대책이 필요하다.

# 6. Glossary

WTOrder  
System  
본 문서에서 설계된 핵심 시스템으로, 고객(Customer), 매장(Store), 주방(Kitchen), 관리자(Admin) 간의 주문 처리 및 데이터 흐름을 통합적으로 관리하는 테이블 오더 기반 주문 시스템을 의미한다.

Customer  
WTOrder System을 사용하는 최종 사용자로, 테이블 디바이스를 통해 메뉴를 조회하고 주문을 생성하며 직원 호출 등의 기능을 수행하는 주체이다.

Kitchen  
고객의 주문을 전달받아 조리를 수행하는 역할을 하는 주체로, 시스템으로부터 주문 정보를 수신하고 이를 기반으로 음식 준비를 진행한다.

Store  
개별 매장을 운영하는 주체로, 메뉴 등록 및 수정, 가격 설정, 품절 관리, 주문 현황 확인 등의 기능을 수행한다.

Admin  
여러 매장의 정보를 통합적으로 관리하는 상위 관리자 역할로, 매장 정보 관리 및 전체 운영 데이터 모니터링을 수행한다.

Database  
시스템에서 사용하는 모든 데이터를 저장하고 관리하는 저장소로, 메뉴 정보, 주문 정보, 사용자 정보 등을 저장하고 조회 및 업데이트를 지원한다.

Menu  
고객이 선택할 수 있는 음식 또는 상품의 목록으로, 이름, 가격, 설명, 이미지 등의 속성을 포함한다.

Order  
고객이 선택한 메뉴와 수량을 포함한 주문 요청 데이터로, 시스템을 통해 처리되어 주방으로 전달된다.

Process  
Order  
고객의 주문이 생성된 이후 데이터 검증, 저장, 전달 등의 과정을 거쳐 주방과 시스템에 반영되는 일련의 처리 과정을 의미한다.

Sold-out  
특정 메뉴가 재고 부족 또는 운영상의 이유로 더 이상 주문할 수 없는 상태를 의미한다.

# 7. References

- Describe all of your references (book, paper, technical report etc).  
- 12pt, 160%.

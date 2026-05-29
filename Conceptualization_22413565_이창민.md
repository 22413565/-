# WTOrder Conceptualization (수정본)

## 핵심 변경사항
- Customer App, Kitchen App, Store App, Admin App 분리
- Store PC Manager 추가
- Kitchen POS 연동
- Store POS 연동
- 테이블 관리 기능 추가

## Business Purpose
WTOrder는 저비용 테이블 오더 시스템으로 고객 태블릿, 주방 태블릿, 매장 태블릿, 관리자 앱을 분리하여 운영 효율성을 높인다.

## System Context
Customer App → WTOrder Server → Database
                     ↓
              Kitchen App + POS
                     ↓
              Store App + POS
                     ↓
             Store PC Manager
                     ↓
                Admin App

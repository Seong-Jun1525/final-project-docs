# 여행다섯시 - 백엔드 프로젝트 구조

> 작성자 : [임성준](https://www.github.com/Seong-Jun1525)

## 유형

### 계층형

```
└── src
    ├── main
    │   ├── java
    │   │   └── com
    │   │       └── example
    │   │           └── demo
    │   │               ├── DemoApplication.java
    │   │               ├── config
    │   │               ├── controller
    │   │               ├── dao
    │   │               ├── domain
    │   │               ├── exception
    │   │               └── service
    │   └── resources
    │       └── application.properties
```

#### 장점

- 프로젝트에 대한 이해도가 낮아도 전반적인 구조를 빠르게 확인 가능

#### 단점

- 하나의 폴더 내에 너무 많은 클래스들이 모이게 됨

### 도메인형

```
└── src
    ├── main
    │   ├── java
    │   │   └── com
    │   │       └── example
    │   │           └── demo
    │   │               ├── DemoApplication.java
    │   │               ├── coupon
    │   │               │   ├── controller
    │   │               │   ├── domain
    │   │               │   ├── exception
    │   │               │   ├── repository
    │   │               │   └── service
    │   │               ├── member
    │   │               │   ├── controller
    │   │               │   ├── domain
    │   │               │   ├── exception
    │   │               │   ├── repository
    │   │               │   └── service
    │   │               └── order
    │   │                   ├── controller
    │   │                   ├── domain
    │   │                   ├── exception
    │   │                   ├── repository
    │   │                   └── service
    │   └── resources
    │       └── application.properties
```

#### 장점

- 연관 코드 별로 모여 있음

#### 단점

- 프로젝트에 대한 이해도가 낮을 경우 구조 파악 어려움

## 적용할 유형

### 도메인형

- 연관 소스 코드끼리 모여 있으므로 참고할 변수나 클래스 등을 빠르게 참고할 수 있음
- 관리하기 편함
- 수업 때 했던 방식이므로 팀원들 전체가 익숙함

```
└── 📁src
    ├── 📁main
    │   ├── 📁java
    │   │   └── 📁com
    │   │       └── 📁kh
    │   │           └── 📁clock
    │   │               ├── 📁aspect (Logging)
    │   │               ├── 📁common (PageNation, File관련 등)
    │   │               ├── 📁config (WebConfig, SecurityConfig 등)
    │   │               ├── 📁interceptor
    │   │               ├── 📁admin
    │   │               │   ├── 📁controller
    │   │               │   ├── 📁domain
    │   │               │   ├── 📁exception
    │   │               │   └── 📁service
    │   │               ├── 📁member
    │   │               │   ├── 📁controller
    │   │               │   ├── 📁domain
    │   │               │   ├── 📁exception
    │   │               │   └── 📁service
    │   │               ├── 📁accommodation
    │   │               │   ├── 📁controller
    │   │               │   ├── 📁domain
    │   │               │   ├── 📁exception
    │   │               │   └── 📁service
    │   │               ├── 📁room
    │   │               │   ├── 📁controller
    │   │               │   ├── 📁domain
    │   │               │   ├── 📁exception
    │   │               │   └── 📁service
    │   │               ├── 📁payment
    │   │               │   ├── 📁controller
    │   │               │   ├── 📁domain
    │   │               │   ├── 📁exception
    │   │               │   └── 📁service
    │   │               ├── 📁review
    │   │               │   ├── 📁controller
    │   │               │   ├── 📁domain
    │   │               │   ├── 📁exception
    │   │               │   └── 📁service
    │   │               ├── 📁daily
    │   │               │   ├── 📁controller
    │   │               │   ├── 📁domain
    │   │               │   ├── 📁exception
    │   │               │   └── 📁service
    │   │               └── 📁chat
    │   │                  ├── 📁controller
    │   │                  ├── 📁domain
    │   │                  ├── 📁exception
    │   │                  └── 📁service
    │   └── 📁resources
    │       ├── 📁mappers
    │       ├── 📁properties
    │       └── application.properties
```

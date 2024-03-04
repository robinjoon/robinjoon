# 기술 스택

1. **`Java`** 
2. **`Spring`**, **`Spring Boot`**
3. **`JPA`**, **`Spring Data JPA`** 
4. **`MariaDB`** , `Mysql` 
5. `Servlet` & `JSP`
# 이력

| 연도 | 활동 |
| --- | --- |
| 2024 ~ 현재 | 우아한테크코스 6기 웹백엔드 과정 |
| 2022 | https://github.com/Goal-achievement-system 백엔드 개발자 |
| 2022 | https://github.com/Great-Student-Manage-System 백엔드 개발자 |
| 2020 ~ 2021 | 홍익대학교 정보보안 동아리 HUST 홈페이지 개발 |
| 2018 | 홍익대학교 정보보안 동아리 HUST 부회장 |
| 2016 ~ 2023 | 홍익대학교 정보보안 동아리 HUST |
| 2016 ~ 2023 | 홍익대학교 컴퓨터정보통신공학과 재학 |
# 프로젝트 목록

## 골키퍼

목표 달성 자극시스템 골키퍼 프로젝트 입니다.

사용 기술 : **`Spring Interceptor`, `ExceptionHandler`**

레퍼지토리 : [https://github.com/Goal-achievement-system/backend](https://github.com/Goal-achievement-system/backend)

### 진행 업무

- **공통 작업 처리를 위한 `Spring Interceptor` 사용**
    - Access Token 을 이용한 사용자 인증 처리 작업은 거의 모든 기능에서 동작해야 하기 때문에 모든 Controller보다 먼저 실행된다는 특성을 가진 `Spring Interceptor` 를 사용했습니다.
- **`Spring Interceptor` 와 `Spring WebMvcConfigurer` 에서 발생한 CORS 설정 문제 해결**
    - CORS 설정이 정상동작하지 않는 문제가 있었습니다.
    - 문제를 해결하기 위해 CORS에 대해 깊이 있게 학습한 후 BurpSuite 를 이용해 패킷을 분석하여 prefligth 요청이 정상처리되지 않아 문제가 발생하는 것을 알아냈습니다.
    - Access Token 관련 처리를 하는 Interceptor 가 prefligth 요청에서도 Access Token을 추출하려 시도해서 발생하는 문제임을 알았고, 예외처리를 해서 수정할 수 있었습니다.
    - 자세한 사항은 [블로그 포스팅](https://www.notion.so/CORS-a320cfb895234bdeb8cc5e7248ac65a2) 에서 확인할 수 있습니다.
- **중복된 예외 작업 처리를 위한 `ExceptionHandler` 사용**
    - Controller 반복적인 try-catch 문이 있었습니다. 중복된 코드는 가독성을 떨어트리고 실수를 유발할 수 있기 때문에 제거해야 했습니다.
    - 이를 위해 예외를 추상화하고 **`ExceptionHandler`** 를 이용해 예외 처리 작업을 Controller에서 분리했습니다.

## 골키퍼 2

기존에 진행했던 골키퍼 프로젝트에 새로운 기능과 기술을 적용한 프로젝트 입니다.

대표 사용 기술 : **`Spring Data JPA`, `GitHub Actions`, `Servlet Filter`, `Spring AOP`, `Spring Interceptor`**

레퍼지토리 : [https://github.com/GoalKeeperV2-0/GoalKeeperV2-backend-](https://github.com/GoalKeeperV2-0/GoalKeeperV2-backend-)

### 진행 업무

- **`Servlet Filter`, `Spring AOP`, `Spring Interceptor` 를 사용한 로깅 시스템 구축**
    - 이전 버전에는 로그를 남기지 않아 새로운 기능을 추가할 때마다 발생하는 오류를 트래킹하기가 어려웠습니다.
    - 이를 해결하기 위해 **`Servlet Filter`**, **`Spring AOP`**, **`Spring Interceptor`** 를 사용해 로깅 시스템을 구축했습니다.
    - 보다 자세한 학습 과정은 [블로그 포스팅](https://www.notion.so/Spring-Boot-REST-API-System-Logging-6a833112c36b4482855de067b255e1c7) 에서 확인할 수 있습니다.
- **객체지향적인 설계를 위한 `Spring Data JPA` 사용**
    - 기존 버전에서는 JdbcTemplate를 사용했기 때문에 SQL 을 직접 작성해야 했고, 비즈니스 로직이 SQL 내부에 숨어들어가기 쉬웠습니다.
    - 이를 해결하기 위해 **`Spring Data JPA`** 를 사용해 SQL 을 직접 작성하지 않고 변경될 가능성이 적은 비즈니스 로직은 엔티티로, 변경되기 쉬운 운영 정책은 서비스에서 구현할 수 있었습니다.
- **자동 배포를 위한 `GitHub Actions` 사용**
    - 기존에는 변경사항이 발생할 때 마다 직접 터미널을 이용해 서버에 접속해 파일을 옮기고 실행해야 했습니다.
    - 그 과정에서 기존에 실행중인 프로세스를 중지하지 않고 실행한다던지, 중지만 하고 새 버전을 실행하지 않는 등의 상황이 자주 발생했습니다.
    - 이를 해결하기 위해 GitHub 에서 제공하는 CI 기능인 **`GitHub Actions`** 와 간단한 Bash Shell Script를 사용해 Push 시 자동으로 빌드 및 테스트 코드 수행 후 서버에 배포되게 했습니다.
- 더 효율적인 API 설계를 위한 고찰
    - 이 시스템에서 사용하는 목표와 인증 이라는 도메인은 일반적인 게시글과 댓글 의 관계처럼 주종 관계입니다. 하지만, 목표 도메인은 인증이 있어야만 사용자에게 제공된다는 차이점이 있습니다.
    - 이런 특이한 도메인 관계에 의해 데이터를 조회하는 방식에 따른 [효율성 차이를 분석](https://www.notion.so/2249852f04a148179bf135373f1d071b)해야 할 필요가 있었습니다.

## 그레잇

소규모 학원 선생님을 위한 학생 관리 시스템 그레잇 프로젝트입니다.

대표 사용 기술 : **`AccessToken`, `RefreshToken`, `Cookie`**

레퍼지토리 : [https://github.com/Great-Student-Manage-System/Backend](https://github.com/Great-Student-Manage-System/Backend)

### 진행 업무

- **좀더 안전하면서도 편리한 인증을 위한 `AccessToken`, `RefreshToken`, `Cookie` 사용**
    - 사용자 인증을 안전하게 하기 위해 **`AccessToken`, `RefreshToken`, `Cookie`**  를 사용했습니다.
    - **`Cookie`** 를 사용하는 과정에서 분명히 백엔드에서 **`Cookie`** 를 설정해 응답을 했지만, 프론트엔드에서 받은 응답에는 **`Cookie`** 가 포함되지 않는 문제가 있었습니다.
    - 몇번의 실험 끝에 브라우저에서만 **`Cookie`** 가 제대로 표현되지 않는 것이고 이는 **`Cookie`** 의 몇몇 속성에 문제가 있었기 때문이었습니다.
    - 자세한 사항은 [블로그 링크](https://www.notion.so/Great-ab2740cf8f6e450684d15e816da65742) 에서 확인할 수 있습니다.

## Hust 홈페이지

동아리 홈페이지 개발 프로젝트

대표 사용 기술 : **`Servlet`, `JSP`, `HTML5`, `BootStrap`, `Jquery`, `WebSocket`, `JDBC`**

레퍼지토리 : [https://github.com/robinjoon/HUST_WEB](https://github.com/robinjoon/HUST_WEB)

### 진행 업무

- **데이터 베이스 연결을 위한 `JDBC` 사용**
    - 회원, 게시글, 댓글 등의 저장을 위해 MariaDB를 사용했고, Java에서 데이터베이스 연결을 위해 JDBC를 사용했습니다.
    - 현대의 Java 진영에서 사용하는 데이터베이스 연결 기술의 원천인 JDBC의 이해를 할 수 있었습니다.
- **동적인 웹페이지 생성을 위한 `Servlet`, `JSP` 사용**
    - 게시글마다 다른 데이터를 보여줘야 하기 때문에 **`Servlet`**, **`JSP`** 를 사용했습니다.
    - 현대의 Spring MVC 프레임워크의 원천 기술인 **`Servlet`** 에 대해 이해할 수 있었습니다.
- **실시간 통신을 위한 `Jquery`와 `WebSocket` 사용**
    - 몇몇 기능의 구현을 위해선 실시간으로 서버와 통신을 수행해야 했습니다.
    - 이를 위해 **`WebSocket`** 을 사용하기로 했고, 브라우저에서 **`WebSocket`** 을 쉽게 사용하기 위해 **`Jquery`** 를 사용했습니다.

## 오클락
### 진행 업무
- **채팅 기능 구현을 위한 `WebSocket` 사용**
    - **`WebSocket`** 을 사용해 채팅 기능을 구현했습니다.
    - **`Spring`**의 **`TextWebSocketHandler`** 를 이용했습니다.
- **민감 정보 제외를 위한 `DTO` 분리**
    - 채팅 상대방의 정보를 조회하는 기능을 구현했습니다.
    - 민감한 개인정보가 포함되는 문제를 해결하기 위해 별도의 DTO를 사용하도록 했습니다.
    - 자세한 사항은 [블로그 포스팅](https://robinjoon.notion.site/DB-3655ea99edd8413790635d4d3abd5e54) 에서 확인할 수 있습니다.

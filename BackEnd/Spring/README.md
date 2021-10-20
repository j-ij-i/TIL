## SpringFramework 등장배경

**EJB(Enterprise JavaBeans)**

- 자체적으로 실행 불가, EJB서버가 반드시 필요
- 기능은 좋지만 테스트, 반드시 해야할 것들이 많이 불편
  → without EJB 등장 (EJB없이도 가능하도록 하는 것이 Spring)

**POJO(Plain Old Java Object)**

- 옛날 자바 형식을 유지하면서 경량 프레임워크를 적용

경량 프레임워크란? ) EJB가 제공하는 서비스를 지원해줄수있는 프레임워크

**POJO + Framework**

- EJB서버와 같은 거창한 컨테이너 필요 X
- 오픈소스 프레임워크
- 모든 플랫폼에서 사용 가능하다.

**Spring Framework**

- 엔터프라이즈 급 애플리케이션을 만들기 위한 모든 기능을 종합적으로 제공하는 경량화 된 솔루션
- DI나 AOP와 같은 기능을 지원
- Enterprise Application 개발 시 복잡함을 해결하는 Spring 의 핵심

## Spring의 구조

- **POJO**
- **PSA**
- **IoC/DI**
- **AOP**

## AOP(Aspect Oriented Programming)

- 관점 지향 프로그래밍
- 자주 쓰는 기능을 모듈화 하기 위해 사용
- **모듈화** : 어떤 공통된 로직이나 기능을 하나의 단위로 묶는 것

### AOP 주요 개념

- **Aspect**: Advice + PointCut 을 합친 기능, 부가기능을 모듈화 함.
- **Target** : Aspect를 적용할 곳.
- **Advice** : 부가기능을 뜻함.
- **JointPoint** : Advice가 적용될 위치와 지점.
- **PointCut** : JointPoint의 상세한 내용, 많은 메소드 중에 부가기능을 적용할 메소드, 시점을 지정.

# MVC 패턴

## Controller

- @Controller annotation과 @RequestMapping 선언으로 사용 가능
- Controller class, Client의 요청 처리
- class타입에 적용
- @RequestMapping - 매핑 동시에 여러개 사용가능
- 같은 URL 요청에도 HTTP method에 따라 구분해서 mapping 가능(get, post 등 구분)
- @RequestParam을 이용해서 parameter 값 mapping이 가능하다.
- @ModelAttribute를 이용해서 View에 사용할 Command 객체 이름을 변경 가능
- @CookieValue를 이용해 Cooking 값, 이름 mapping 가능

## View

- ViewResolver - 논리적 view와 실제 jsp파일을 매핑 해줌. (servlet-context.xml에 존재)
- **ModelAndView**를 이용해서 View 이름 명시적 지정, Model이 없을 땐 **String**으로 넘겨 줌.
- 자동으로 RequestMapping 루트가 이름이 되는 경우 👉 1️⃣ 리턴 타입이 Map, Model 인 경우 2️⃣ 리턴타입 void이면서 ServletResponse나 HttpServletResponse타입의 parameter가 없는 경우
- Redirect View - View에 **redirect:** 접두어를 붙이면 지정한 페이지로 redirect 된다.

## Model

- View에 전달, 담아야 하는 데이터
- Map, ModelMap, Model을 통해 설정 가능 → 결국은 모두 Map형식!
- @PathVariable을 이용해서 URI 템플릿 이용 가능 (RESTful 방식)

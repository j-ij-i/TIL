# Vue.js

![image](https://user-images.githubusercontent.com/46212602/140727551-024709fe-ab3e-496f-ba48-adcafcc2e055.png)

## Vue란?

- Even You에 의해 2014년도에 발표됨.
- Google에서 Angular로 개발하다가 가벼운 걸 만들어 보고 싶은 생각으로 시작한 개인 프로젝트로 탄생
- 사용자 인터페이스를 만들기 위한 진보적인 프레임워크

## 특징

- Approachable (접근성)
- Versatile (유연성)
- Performant (고성능))

## MVVM Pattern

- **Model** + **View** + **iewModel**
- Vue.js의 패턴은 기본적으로 MVVM 패턴을 가짐.
- **Model** : 순수 자바스크립트 객체
- **View** : 웹페이지의 DOM
- **VieWModel** : Vue의 역할
- 기존에는 JS의 JQuery 등과 같은 라이브러리로 View에 접근하였지만 Vue는 view와 model을 연결하고 자동으로 바인딩해 양방향 통신이 가능하게 함.

## Vue Instance

- **el** : Element, Vue가 적용될 요소
- **data** : Vue에서 사용하는 정보, 객체 or 함수의 형태를 가지고 있음.
- **template** : HTML, CSS등의 마크업 요소를 정의하는 속성
- **methods** : 화면 로직 제어와 관련된 method들 정의, 이벤트 처리와 같이 전반적 화면 동작 로직을 추가
- **created** : Vue Instance가 생성되자마자 실행할 로직을 정의.
- **Instance 생성** : 뷰 라이브러리 로딩 -> 인스턴스 객체 생성 -> 특정 화면 요소에 인스턴스 붙이기 -> 인스턴스 내용이 화면요소로 나타남 -> 바뀐 화면을 사용자가 최종 확인 가능

## Vue Life Cycle

### 1. Create (Instance의 생성)

- beforeCreate
- created

### 2. Mount (Instance를 화면에 부착)

- beforeMount
- mounted

### 3. Update (Instance의 내용 갱신)

- beforeUpdate
- updated

### 4. Destroy (Instance 소멸)

- beforeDestroy
- destroyed

## Directives

- **v-** 접두사가 있는 특수 속성, for를 제외하고 단일 JS표현식이 되며 DOM에 적용된다.
- **v-text** : innerText 속성에 연결.
- **v-html** : {{}}속 HTML을 텍스트가 아닌 **실제 HTML**으로 출력해 줌.
- **v-once** : 데이터 변경 시 업데이트 되지 않는 일회성 보간 작동
- **v-model** : **양방향** 바인딩 처리를 위해서 사용, Model과 ViewModel사이 데이터를 바인딩하는 디렉티브(한글의 경우, 한글자가 넘어가야지 적용->UNICODE문자 특성)
- **v-bind** : 엘리먼트 속성과 바인딩 처리, 약어 `":"`로 표현 가능
- **v-show** :
- **v-if** :
- **v-else-if** :
- **v-else** :
- **v-for** :
- **v-cloak** :
- **v-on** : 약어 `"@"`로 표현 가능

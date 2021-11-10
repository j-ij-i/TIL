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
- **v-model** : **양방향** 바인딩 처리를 위해서 사용, Model과 ViewModel사이 데이터를 바인딩하는 디렉티브(한글의 경우, 한글자가 넘어가야지 적용->UNICODE문자 특성) ex) `v-model.trim` (공백제거), `v-model.lazy` (엔터칠 때 전송), `v-model.number` (자동으로 숫자로 형변환)
- **v-bind** : 엘리먼트 속성과 바인딩 처리, 약어 `:`로 표현 가능
- **v-show** : 조건에 따라 화면을 랜더링 하며 style의 display를 변경한다. false일 경우에 display : none 적용
- **v-if**, **v-else-if**, **v-else** : 조건에 따라 엘리먼트를 화면에 렌더링, false일 경우 엘리먼트 삭제됨.
- **v-for** : 배열이나 객체의 반복에 사용, 배열보다 1개 많게 설정해주면 자동으로 index가 나타남. (v-if와 같이 사용을 권하지 않음, for가 if보다 우선순위가 높기 때문에 if를 거치지 않은 불필요한 for문이 나오기 때문에)
- **v-cloak** : Vue Instance가 준비될 때까지 mustache 바인딩을 숨기는데 사용, Vue Instance가 준비되면 v-cloak는 제거.
- **v-on** : DOM Event를 받기 위해 사용, method의 이름으로 받아오며 약어 `@`로 표현 가능

## Vue method

- method안에서 data를 this.데이터이름 으로 접근 가능

## Vue filter

- 화면의 텍스트의 형식을 쉽게 변환해주는 기능
- `filter`를 이용하여 표현식에 새로운 결과 형식을 적용
- 중괄호 보간법 : `{{ message | index }}`
- v-bind 표현법 : `<div v-bind:id="message | index"></div>`
- `{{ a || b1 || b2 }}` 와 같이 체이닝도 가능, 순서대로 작동

## Vue computed 속성

- `computed`는 기능이 아니라 값이며 특정 데이터의 변경사항을 실시간으로 처리해준다.
- 변경된 데이터가 없을 경우 캐싱된 데이터를 반환해준다.
- `method` 형태로 작성하지만 property처럼 사용된다.

## computed VS method 차이점

- `computed`는 실행할 때 값을 캐싱하여 저장해놓기 떄문에 3번 호출되어도 값이 바뀐 1번만 실제 실행되고 나머지는 캐싱된 값을 반환해준다.
- 반면 `method`는 호출할 때마다 실행되므로 3번을 실행하면 그대로 3번 실행이 된다.
- `computed`는 내부의 값이 바뀌었을때만 실행이 된다.

## Vue watch 속성

- Vue Instance 의 특정 property가 변경될 때마다 콜백 함수 설정.
- `watch`는 newVal, oldVal을 받아 이전 값과 새로운 값을 비교한다.
- 바뀌는 부분 뿐만 아니라 다른 데이터들 까지 조작해야할 때 watch 이용 -> trigger처럼 사용

## watch VS computed

- `computed`는 종속된 data가 변경되었을 경우 다시 그 data를 계산하여 캐싱작업을 해줌.
- `watch`는 data가 변경될 때 다른 data도 변경하는 작업을 한다.

## Vue Component

- Vue의 가장 강력한 기능 중 하나, 코드를 캡슐화 함
- SPA(Single-Page Applications)가 가능하게 됨.

## Axios

- Axios는 **Vue에서 권고하는 HTTP 통신 라이브러리**
- **Promise기반**의 HTTP 통신 라이브러리, 다른 통신 라이브러리에 비해 문서화가 잘 되어있고 API가 다양하다.
- **Promise** : 데이터를 요청하고 받아올 때까지 기다렸다가 화면에 나타나는 로직을 실행
- axios.get(URL) -> Promise 객체를 Return 받는다.
- return 받은 promise 객체에서 then, catch를 사용해 데이터를 받는다.

## Axios 대표

- `axios.get('URL 주소').then().catch()`
- `axios.post('URL 주소').then().catch()`
- `axios({옵션속성})`
- 계속되는 `then` 중복을 막기위해 `async, await` 등장 및 사용

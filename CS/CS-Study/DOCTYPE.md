# DOCTYPE

- DOCTYPE에 대하여 설명하시오
- meta 태그에 대해서 알고 있나요?
- meta 태그의 요소에 대해서 아는대로 말해보세요

## DOCTYPE에 대하여 설명하시오

- **Document Type의 약자**로, **HTML**이 어떤 버전으로 작성이 되었는지 선언하여 웹 브라우저가 올바르게 작동하는 역할을 한다.
- 줄여말해 DTD라고 불린다. ( DTD는 Document Type Definition의 약자이며 문서형식을 정의해주는 것을 뜻한다.)
  - **HTML**(Hypertext Markup Language)
    - **SGML**의 응용
    - **데이터가 어떻게 보이질지에 초점**
    - 동일한 데이터를 표시하고 꾸미는데 사용
  - **SGML**(Standard Generalized Markup Language)
    - 마크업 언어를 생성하기 위한 메타 마크업 언어
    - **다른 마크업 언어를 기술하기 위한 마크업 언어**
    - HTML과 달리 마크업을 사용자가 정의할 수 있음
  - **XML**(Extensible Markup Language)
    - HTML의 한계를 극복하고 SGML의 복잡함을 해결하는 방안으로 탄생
    - 마크업 언어를 정의하기 위한 언어, 확장이 가능한 언어
    - 웹에서 디스플레이 표준을 HTML로 한것처럼 데이터의 표준으로 만들기 위한 노력
    - 데이터가 무엇인지에 초점이며 **데이터를 구조화** 하는데 사용
  - **XHTML**(Extensible Hypertext Markup Language)
    - **HTML과 동등한 표현 능력을 지닌 마크업 언어로, HTML보다 엄격한 문법을 가짐**
    - XML의 응용
    - HTML을 사용하면 할 수 있으나 XHTML로는 불가능 한것도 있고, XHTML로는 가능하지만 HTML로는 불가능 한 것도 있음 ex) `<br><br/>`태그

### HTML 4.01에서 선언하는 세 가지 방법

1. **Strict mode**

   - 가장 표준이 되는 DTD
   - 확장된 어트리뷰트를 허용하지 않는다.
   - 배경색 , 글자색등의 일정한 조건에 따른 어트리뷰트를 인정하지 않는다. (bgcolor, font태그의 color)
   - mobile html에 최적

   ```jsx
   <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
   ```

2. **Transitional**

   - 일반적으로 가장 많이 쓰이는 DTD
   - 확장된 어트리뷰트를 호환한다.
   - 각 브라우저에 따른 DTD를 호환한다.
   - **Strict**보다 로딩속도는 느리다.
   - **Strict**보다 표준안에 가깝지는 않다.

   ```jsx
   <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
   ```

3. **Frameset**

   - 프레임셋을 만들때 사용하는 DTD
   - 확장 및 프레임에 사용가능한 모든 내용을 포함한다.

   ```jsx
   <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" "http://www.w3.org/TR/html4/frameset.dtd">
   ```

### HTML5에서는 선언 방법

- **`<!DOCTYPE html>`**

### 사용하는 이유

만약 문서의 상위에 **DOCTYPE 태그를 생략**하면 웹 브라우저가 **표준 모드(Standards mode)**가 아니라 **비표준 모드(Quirks mode)**로 렌더링된다.

**비표준 모드(Quirks mode)**를 이용하면 비표준 CSS문법을 사용하여오래된 웹 페이지를 최신 버전에 브라우저에서 깨져 보이지 않게 않지만표준이 아닌만큼 최신 웹 브라우저에서 **크로스 브라우징에 어려움**을 겪는다.

- **표준 모드 (Standard mode)** : **W3C 표준**에 따라 렌더링, 표준 문법 사용
- **비표준 모드 (Quirks mode)** : **오래된 브라우저**의 행동 모방하여 렌더링, 비표준 문법 사용

## meta 태그에 대해서 알고 있나요?

- HTML 문서의 맨 위쪽에 위치하는 태그(tag)로, HEAD 태그 사이 또는 뒤에 있어도 되지만 반드시 BODY 태그 앞쪽에 위치해야 한다.
- 브라우저와 검색 엔진을 사용할 수 있도록 웹 문서의 정보를 포함하고 있다.
- 웹페이지(Web page)의 요약이므로 상당히 중요하다고 할 수 있다.

## meta 태그의 요소에 대해서 아는대로 말해보세요

### meta 태그 속성

| http-equiv ="항목명" | - 웹 브라우저 서버에 명령을 내리는 속성

- name 속성을 대신해 사용할수 있음
- html 문서가 응답 헤더와 함께 웹 서보로 부터 웹 브라우저에 전송되었을때만 의미를 가짐
- | content 속성의 정보 / 값을 위한 HTTP header를 제공 |
  | -------------------------------------------------- | ------------------------- |
  | content = "정보 값"                                | - meta 정보의 내용을 지정 |
- name 속성과 http-equiv와 연관된 값을 줌. |
  | name = "정보 이름" | - 몇 개의 meta 정보의 이름을 정할 수 있으며 지정하지 않으면 http-equiv 와 같은 기능 |

### meta 태그 요소

1. Keywords (검색엔진에 의해 검색되는 단어 지정)

2. Description(검색 결과에 표시되는 문자 지정)

3. robots (검색 로봇 제어)

4. charset (문자 코드의 종류 설정)

5. Date (날짜- 제작일)

6. Distribution(배포자)

7. Copyright (저작권)

8. subject (홈페이지 주제 지정)

9. viewport (모바일 반응 페이지)

### 참고 링크

[https://inpa.tistory.com/entry/HTML-%F0%9F%93%9A-meta-%ED%83%9C%EA%B7%B8-%EC%A0%95%EB%A6%AC](https://inpa.tistory.com/entry/HTML-%F0%9F%93%9A-meta-%ED%83%9C%EA%B7%B8-%EC%A0%95%EB%A6%AC)

[http://www.tcpschool.com/html-tags/meta](http://www.tcpschool.com/html-tags/meta)

[https://seo-ox3.tistory.com/44](https://seo-ox3.tistory.com/44)

[https://kyoung-jnn.tistory.com/entry/HTML-CSS-DOCTYPE-과-표준-비표준-모드-Standard-Quirks-mode](https://kyoung-jnn.tistory.com/entry/HTML-CSS-DOCTYPE-%EA%B3%BC-%ED%91%9C%EC%A4%80-%EB%B9%84%ED%91%9C%EC%A4%80-%EB%AA%A8%EB%93%9C-Standard-Quirks-mode)

[http://itnovice1.blogspot.com/2018/12/xhtml-xml-sgml.html](http://itnovice1.blogspot.com/2018/12/xhtml-xml-sgml.html)

[https://tuhbm.github.io/2017/08/21/doctype/](https://tuhbm.github.io/2017/08/21/doctype/)

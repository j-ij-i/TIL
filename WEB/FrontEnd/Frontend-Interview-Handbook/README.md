# FrontEnd-Interview-Handbook

## CSS

### 1. CSS 선택자의 특정성은 무엇이며 어떻게 작동하나요?

- 어떠한 스타일이 브라우저의 엘리먼트에 적용될 것인지를 결정하는 일종의 규칙입니다. 더 높은 점수의 CSS 스타일이 엘리먼트에 적용됩니다.
- 이러한 개념을 이해하지 못하면 !important로 우선순위를 정해줘야한다. ⇒ 좋지 않은 관행이지만 CSS framework를 사용할때는 스타일 override를 위해서 인정해준다.

- 선택자 우선순위
  1. 인라인 스타일 속성 (HTML에 직접 style을 적용한 속성)
  2. ID 셀렉터
  3. 클래스, Pseudo클래스 속성 셀렉터
  4. 엘리먼트 셀렉터

순으로 특정성(Specifity)을 가져 적용됩니다.

[https://velog.io/@jakeseo_me/프론트엔드-인터뷰-문제-답해보기-3-CSS-선택자-특정성](https://velog.io/@jakeseo_me/%ED%94%84%EB%A1%A0%ED%8A%B8%EC%97%94%EB%93%9C-%EC%9D%B8%ED%84%B0%EB%B7%B0-%EB%AC%B8%EC%A0%9C-%EB%8B%B5%ED%95%B4%EB%B3%B4%EA%B8%B0-3-CSS-%EC%84%A0%ED%83%9D%EC%9E%90-%ED%8A%B9%EC%A0%95%EC%84%B1)

### 2. `Resetting`과 `Normalizing` CSS의 차이점은 무엇인가요? 당신은 무엇을 선택할 것이며, 그 이유는 무엇인가요?

- `Resetting` : 브라우저별로 태그의 기본 스타일이 다르기 때문에 기본적인 것들을 초기화해서 사용한다. 브라우저별로 최대한 비슷한 웹페이지 작성이 가능하다.

```python
* {
marin: 0;
padding: 0;
border: none;
}
```

- `Normalizing` : 리셋시키는 방법이 아니라 이를 유지하고, 이용하려는 스타일링 방법이다.

```python
h1 {
font-size: 2em;
margin: 0.67em 0;
}
```

- 커스텀마이징이 많이 필요할 경우 `Resetting`, 기본 스타일과 크게 차이점이 없을 경우 `Normalizing`

[https://sapjil.net/resetcss-normalizecss/](https://sapjil.net/resetcss-normalizecss/)

### 3. `float`가 어떻게 작동하는지 설명하세요.

- CSS 위치 지정 속성, float 요소는 페이지의 흐름의 일부가 되며 absolute와 달리 다른 요소의 위치에 영향을 준다.
- left, right, both 속성으로 위치를 지정해줄 수 있다.
- .clearfix 를 통해 float를 지울 수 있다.

### 4. `z-index`와 스태킹 컨텍스트(stacking context)가 어떻게 형성되는지 설명하세요.

- z-index는 레이어의 순서를 말하며 position에서 static이 아닌값에만 영향을 준다. (flex에서는 static인 경우에도 작동한다.)
- z-index수가 클수록 위로 올라오며
- 스택 컨텍스트는 레이어들을 포함하는 요소이며 z-index는 동일한 컨텍스트에 있을 때 비교된다.

**스태킹 컨텍스트 만드는 방법들**

- 상대 위치 또는 절대 위치를 z-인덱스와 결합하여 스택 컨텍스트를 만드는 방법
- opacity를 1보다 작은 값으로 설정
- position를 fixed 또는 sticky으로 설정(이 값에는 z-index가 필요하지 않습니다!)
- normal 모드 대신 mix-blend-mode 사용
- display: flex 또는 display: grid 컨테이너 내부의 자식에 z-인덱스 추가
- transform,filter,clip-path,perspective 사용
- opacity 또는 transform과 같은 값으로 will-change 사용
- `isolation:isolate`를 사용하여 컨텍스트를 명시적으로 생성

**isolation을 이용하여 스택 컨텍스트 생성 장점**

- z-index 값이 필요하지 않다.
- position 기본값(static)에서 사용할 수 있다.
- 자식요소의 렌더링에 영향을 미치지 않는다.
- BUT IE에서는 사용불가(**`transform: translate(0px);` 를 대체로 사용**)

[https://itchallenger.tistory.com/660](https://itchallenger.tistory.com/660)
[https://velog.io/@yiseul/z-Index와-Stacking-contexts](https://velog.io/@yiseul/z-Index%EC%99%80-Stacking-contexts)

### 5. BFC(Block Formatting Context)와 그 작동 방식을 설명하세요.

- 웹페이지의 블록 레벨 요소를 렌더링하는데 사용되는 CSS의 비주얼 서식 모델
- 블록 레벨 요소가 포함되는 **서식모델**
- **BFC 생성 조건** ( 하나 이상을 충족하면 됨 )

- 루트 혹은 이를 포함하는 요소
- float가 none이 아니면서 clear 되지 않은 경우
- position이 absolute / fixed
- display가 inline-block / tabel-cell / tabel-caption
- overflow가 visible이 아님
- display가 flex / inline-flex

**BFC 활용**

1. 마진겹침 제거하기
   - 태그 사이에 10px의 마진을 줄 때 마진겹침으로 인해 20px이 아닌 10px이 된다. 이 때 새로운 BFC를 생성해서 집어넣으면 마진겹침을 해결할 수 있다.
2. float된 요소들 포함하기
   - 보통 float된 요소를 포함하기 위해선 .clearfix 핵을 사용하지만 새로운 BFC를 생성함으로도 해결할 수 있다.
3. float된 요소를 감싸는 텍스트를 분리하기
   - p 태그로 새로운 BFC를 생성하여 텍스트가 float 된 요소를 감싸지 않도록 한다.

[https://hceaan.tistory.com/101](https://hceaan.tistory.com/101)

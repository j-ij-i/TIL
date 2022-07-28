# 이미지 랜더링 등

- 이미지 크기가 클 경우 렌더링 속도가 느려질텐데 이를 개선하기 위한 방법
- UI란 무엇인지 설명하시오
- UI / UX 비교
- SVG 장점과 단점
- SVG 내부 도형에 대해 아는게 있나요?

## 이미지 크기가 클 경우 랜더링 속도를 개선하기 위한 방법

[https://velog.io/@hustle-dev/웹-성능을-위한-이미지-최적화](https://velog.io/@hustle-dev/%EC%9B%B9-%EC%84%B1%EB%8A%A5%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%9D%B4%EB%AF%B8%EC%A7%80-%EC%B5%9C%EC%A0%81%ED%99%94)

- 이미지 `폭`을 조절하라.
- 최적화된 이미지 `포맷`을 사용하라.
- `<img>`에 `width, height` 값을 선언해 `Reflow`를 방지하라.
- `여러 버전의 이미지`를 제공하라.
- 이미지 크기 조절 `툴`을 사용하라.
- `Image CDNs`을 사용하라
- `CSS Sprite` 기법을 사용하라.
- `lazy loading`을 활용하라.

## UI / UX 비교

- **UI는 시각적인 디자인을, UX는 그 시각적인 디자인을 필두로 사용자가 편리함을 느끼게끔 만들어주는 것을 의미한다.**

## SVG 장점과 단점

### SVG 정의

- Scalable Vector Graphics의 약자로, 2차원 벡터 그래픽을 표현하기 위한 XML 기반 마크업 언어
- 1999년 W3C의 주도하에 개발된 오픈 표준 벡터 그래픽 파일 형식
- 점과 점사이의 계산을 통해서 그리는 그래픽

### SVG 장점

- 확대해도 절대 깨지지 않고 절대 늘어나지 않는다.
- JPG, PNG 비트맵 이미지로 사용안하고 SVG로 많이 쓰인다.

### SVG 단점

- 모양이 복잡할 수록, 그림 구성하는 포인트 많을수록 용량이 커져서 성능도 떨어진다.

### SVG 사용법

1. `<img>`에 넣을 수 있음

```jsx
<img src="/resources/images/test.svg" />
```

2. CSS Background로 사용

- class에 아래와 같이 css background로 넣어주고, html 태그 요소의 class로 넣어줌

```jsx
url('/resources/images/test.svg');
```

3. SVG를 직접 HTML에 inline으로 삽입

```jsx
<body>
  {' '}
  <svg>
    {' '}
    <rect x="0" y="0" width="100" height="100"></rect>{' '}
  </svg>{' '}
</body>
```

4. `object`태그를 이용

```jsx
<object data="/resources/images/test.svg" type="image/svg+xml"></object>
```

## SVG 내부 도형에 대해

- SVG는 직사각형(rect), 원(circle), 타원(ellipse), 직선(line), 폴리 라인(polyline), 다각형(polygon)과 같은 기본 모양을 그릴 수 있는 요소 세트를 제공한다.
- 각 요소는 좌표 위치(x, y), 크기(width, height) 등 속성을 설정할 수 있다.

### 사각형(rectangle)

- <rect> 요소는 사각형을 그립니다. 너비(width), 높이(height), 색상(fill) 등을 속성으로 설정할 수 있다.

```jsx
<svg>
  <rect width="480" height="240" fill="#3d87fb" />
</svg>
```

### 원(circle)

- <circle> 요소는 원을 그립니다. 원의 중심(rx, ry), 반지름(r), 색상(fill) 등을 속성으로 설정할 수 있다.

```jsx
<svg>
  <circle cx="200" cy="200" r="50" fill="#3e295e" />
</svg>
```

### 타원(Ellipse)

- <ellipse> 요소는 타원을 그립니다. 타원을 그리기 위한 반지름(rx, ry) 속성을 설정할 수 있다.

```jsx
<svg>
  <ellipse
    cx="200"
    cy="200"
    rx="50"
    ry="100"
    fill="#dd3742"
    stroke="#b13138"
    stroke-width="8"
  />
</svg>
```

### 직선(Line)

- <line> 요소는 직선을 그립니다. 선의 시작점(x1, y1)과 끝점(x2, y2) 속성을 설정할 수 있다.

```jsx
<svg>
  <line x1="440" y1="40" x2="120" y2="200" stroke-width="5" stroke="#26b2a2" />
</svg>
```

### 폴리라인(Polyline)

- <polyline> 요소는 2개 이상의 점들이 직선으로 연결된 도형 그린다.
- 각 점들의 위치(points) 속성을 설정할 수 있습니다. 각 점은(x,y) 공백으로 구분된다.

```jsx
<svg>
  <polyline
    points="0,0 40,40 40,80 80,80 80,120 120,120 160,160"
    fill="none"
    stroke="#b38fac"
    stroke-width="6"
  />
</svg>
```

### 다각형(Polygon)

- <polygon> 요소는 3개 이상의 점들이 연결된 다각형을 그린다.

```jsx
<svg>
  <polygon
    points="50,5 100,5 125,30 125,80 100,105 50,105 25,80 25,30"
    fill="#4b6eec"
  />
</svg>
```

### 참고링크

[https://superfelix.tistory.com/604](https://superfelix.tistory.com/604)

[https://a11y.gitbook.io/graphics-aria/svg-graphics/svg-basic-shapes#line](https://a11y.gitbook.io/graphics-aria/svg-graphics/svg-basic-shapes#line)

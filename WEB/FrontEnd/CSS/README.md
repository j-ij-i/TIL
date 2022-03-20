# CSS 기초

**본 내용은 _‘김버그의 CSS는 재밌다’_ 강의를 정리하였습니다.**

**모든 영역들은 box로 정의할 수 있다.**

> **안쪽 여백** - padding

> **테두리** - border
>
> - border 정의(굵기 스타일 색)
> - border-radius (각 굵기)

> **바깥족 여백** - margin

## **주요 개념**

**모든 영역들은 box로 정의할 수 있다.**

⇒

> **안쪽 여백** - padding

> **테두리** - border
>
> - border 정의(굵기 스타일 색)
> - border-radius (각 굵기)

> **바깥족 여백** - margin

![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled.png)

### **속기형으로 정의하기**

- 순서 : top right bottom left
  - ex) padding: 10px 20px 40px → right, left 둘이 20px로 적용됨

**box-sizing** : content-box로 되어있으면 content 내에서만 적용됨.

**border-box**로 해야지 전체영역기준으로 잡음

```css
//**모든 css의 첫번째 선언은 이렇게!**
* {
  box-sizing: border-box;
}
```

### \*B**ox model\*** 종류

**display** 속성 : **box 종류를 선언**

- **block**
- **inline**
- **inline-block**
- **flex**

### **block → 길막 개념?**

- width를 선언하지 않을 경우에는 width는 부모 content-box의 100%가 됨.
- 따로 width 선언하면 남은 공간은 margin으로 자동으로 채움.
- margin: 0 auto; → 위아래는 마진 0, 왼쪽 오른쪽은 오토로 적용됨.
- margin-left: auto; 왼쪽으로 마진 설정, right까지하면 가운데 정렬
- 부모도 height 따로 설정안하면 child의 height 속성으로 됨.

![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%201.png)

### **inline** → **흐름**

- 공간이 부족하면 아래로 내려감( text문서 작성느낌)
- 크기설정, 패딩,마진 위아래 모두 사용불가 (오른쪽 왼쪽은 사용가능)

![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%202.png)

![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%203.png)

<aside>
💡 **block** (면, 영역개념) / **inline** (선, 흐름개념)

</aside>

### **inline block** (block과 inline 개념을 둘다 가진 짬짜면 같은..?!)

- 기본적으로는 가로로 흐르고 영역도 사용가능
- width, height 등 block에서 사용이 안되는 것이 다 사용가능!

![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%204.png)

### **Float** : 가로배치를 위해 설정

- float로 설정하면 뜨게 되어 부모, 형제도 찾지를 못함.
- float로 바꾸면 display는 block으로 설정됨.
- box display일떄 사용할 수 있는 것들이 사용가능 ex) width, height 등등
- 하지만 남은 공간은 margin으로 채워지지는 않음, 위로 뜨게됨
- 결론 - **레이아웃 와장창;;**
- 어떻게 와장창을 잡을까요
  - 쉽게 하는 방법
    - 부모에 overflow: hidden을 하면 부모가 집나간 자식을 찾을 수 있음
  - 정석 방법
    - clearfix 사용
    - clear 속성은 오로지 float를 고치기 위한 존재
    - clear left를 걸면 float left걸린애들을 다 찾게됨.
  +공간을 채워넣을 가상요소 넣기(**pseudo**)
  - ::before
  - ::after
  ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%205.png)

![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%206.png)

![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%207.png)

![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%208.png)

### Position

<aside>
📃 **static, relative, absolute, fixed**, sticky로 나눔
(sticky는 지원안되는 경우가 많아 제외)

</aside>

- **static** : 기본값, 가장 일반적인 상태
- **relative** : float처럼 위치가 바뀌지만, 기존의 위치는 유지됨. 다른요소한테 영향안줌
  - 이미지 예시
    ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%209.png)
- **absolute** : float 사용과 비슷한 현상으로 발생
  - display가 block으로 변화됨. 부모가 못찾아서 넓이 인식못함
  - 자신이 기준으로 삼고싶은 기준을 새로 삼을 수 있음
  - absolute는 자신의 조상중에 static이 아닌 곳으로 기준점을 잡음.
- **fixed** : 자신의 기준점이 **viewport**기준으로 잡힘.

## 🧡*Flexbox*

**flex는 완벽?! 거의 이것만 씀! 중요!**🚨

- 가로로 정렬, 세로로 정렬. 한줄안에 정렬만 생각하면 됨.
- `display : flex` 적어주면 사용가능
- 정렬을 감싸고자 하는 요소한테 display: flex를 줘야함
- **flex-direction** 속성 → 정렬 방향 선언
- `/* row | row-reverse | column | column-reverse */`
- **axis** - 축 : flex 방향을 따라서 main axis, cross axis가 생성됨.
- EX)`flex-direction : row` 선언
  - _axis_ 방향
    ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2010.png)
- EX)`flex-direction : column` 선언
  - axis 방향
    ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2011.png)
- EX)`flex-direction : row-reverse`선언
  - **axis** 방향
    ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2012.png)
- EX)`flex-direction : column` 선언
  - **axis** 방향
    ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2013.png)
- `flex-warp:nowrap` - 강제로 사이즈를 줄여서 한줄로 정렬해버림
- `flew-wrap:wrap` - 사이즈를 줄이지 않고 여러줄로 만듬

### 🪟 axis를 고려하여 정렬

- main 방향 정렬 속성 : `justify-content`
  - **justify-content**
    - **flex-start** : flex라인의 시작위치로 정렬
      - EX) `flex-direction : row`일때
        ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2014.png)
    - **flex-end** : flex라인의 끝위치로 정렬
      - EX) `flex-direction : row`일때
        ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2015.png)
    - **center** : 가운데 정렬!
      - EX) `flex-direction : row`일때
        ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2016.png)
    - **space-between** : 요소들 사이에 간격을 같게 해줌!
      - EX) `flex-direction : row`일때
        ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2017.png)
    - **space-around** : 요소 양옆 마진을 같게 정렬 해줌
      - EX) `flex-direction : row`일때
        ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2018.png)
- cross 방향 정렬 속성 : `align-items` / `align-content`

  - **align-items**
    - **center** : cross 방향으로 가운데 정렬
      - EX)`flex-direction : row`일때
        ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2019.png)
        ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2020.png)
    - **flex-end,flex-start** 사용 가능
    - space-between, space-around 둘 다 사용 불가
  - **align-content**
    - 각각의 flex라인이 아니라 전체를 기준으로 정렬됨
    - align-items와 달리 전체를 기준으로 하기 때문에 space-between, space-around 모두 사용 가능
    - center
      - `flex-direction : row`일때
        ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2021.png)

- **order**
  - `order: N ;`으로 주면 순서
  ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2022.png)
  ### **💡 작업 꿀팁**
  ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2023.png)
  ### **Media Query**
  **반응형웹 고려!**
  → `<meta name=”viewport” content=”width=device-width”>` 작성
  ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2024.png)
  ![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2025.png)
  → vh는 뷰포트에서 차지하는 비율
  - 100vh = 100%
  - 가로는 vw
  - 주로 vh를 많이 사용

![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2026.png)

### Typography

![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2027.png)

**font-size**

- **px**: 절대단위
- **em**: 상대단위 - 대문자 M사이즈로 기준, **실제로 적용된 폰트 사이즈 - 1em**
- **rem**: 상대단위 - html의 em, html에 적용된 폰트사이즈 기준 - **1rem**

**line-height** :줄간격

- px
- **em**
- rem
- **line-height 를 적용하면 글자는 가장 가운데로 배치됨**

**letter-space** : 자간

- px
- **em**

**font-family**

![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2028.png)

순서대로 적용시킬 폰트 선언

- poppins 없으면 ㅁㅁ, ㅁㅁ 없으면 sans-serif

**font-weight**

![Untitled](CSS%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20ba163/Untitled%2029.png)

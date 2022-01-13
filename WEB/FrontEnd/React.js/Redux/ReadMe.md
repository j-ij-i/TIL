## **Redux**

- `React`에서 `Redux`에 대한 내용이 많아 강의를 들으면서 계속 참고할 내용들을 정리해보았다.
- `html`에게 뭔가 바뀌었다고 알려주기 위해 함수를 사용
- `Store`는 data를 저장하는 곳
- `CreateStore`는 reducer를 요구함.
- `Reducer`는 data를 modify 해주는 함수로 reducer가 return하는 것은 application에 있는 data가 됨.
- `Action` : `redux`에서 function을 부를 때 쓰는 두 번째 parameter 혹은 argument으로 reducer와 소통하기 위한 방법
  - Reducer에게 Action을 보내는 방법 : store.dispatch({key: value});
- `reducer` : 현재 상태(state=0, action)의 application과 함께 불려지는 function (state=0, action)
- `return`하는 것은 application의 state가 됨
- `action` : reducer와 소통하는 방법으로 Object여야 하며 그 key 이름은 항상 type임 (바꿀 수 없음)
- `dispatch` : reducer에게 action을 보내는 방법
  - ex) countStore.dispatch({type:ADD});
- `subscribe` : store가 변화되면 인자값의 함수를 실행
  - ex) countStore.subscribe(onChange);
- `if`, `else if`보단 `switch`가 자주 쓰임
  `switch(action.type){ case : a return a' default: return default' }`

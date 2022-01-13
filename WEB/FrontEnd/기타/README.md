#### **yarn**

- 기존에는 `npm`만을 이용해서 라이브러리들을 받았는데 `React`를 공부하면서 `yarn`을 사용하게 되어서 조사해보았다.
- `Facebook`에서 만든 자바스크립트 패키지 매니저
- `npm`의 단점을 느꼈기에 이를 향상시키기 위해 등장
  - `npm` 단점 : **속도(performance), 안정성(stability), 보안성(security)**
    - **속도** 다운받은 패키지 데이터를 캐시(cache)에 저장하여, 중복된 데이터는 다운로드하지않고, 캐시에 저장된 파일을 활용, 패키지를 설치할 때 **병렬**로 처리하기 때문에 **performance와 speed가 증가(npm은 순차적으로 설치)**
    - **안정성/보안성** npm은 패키지가 설치될 때 자동으로 코드와 의존성을 실행할 수 있도록 허용/ yarn은 yarn.lock이나 package.json에 설치만 하여

#### yarn 명령어

- **yarn init** : package.json 생성
- **yarn or yarn install** : package.json 파일 및 해당 종속성에 나열된 모든 모듈을 설치
- **yarn add package_name@버전** : 특정 패키지의 특정 버전 설치
- **yarn add 주소** : 특정 저장소 내 패키지 설치. 주로 github을 이와 같이 설치합니다.
- **yarn global add package_name** : 옵션. 글로벌로 설치. 로컬의 다른 프로젝트도 이 패키지를 사용 가능하게 됩니다.
- **yarn remove** : 패키지 삭제 명령어입니다.
- **yarn upgrade** : 설치한 패키지들을 업데이트해줍니다.
- **npm dedupe** : 중복 설치된 패키지들을 정리해주는 명령어입니다.

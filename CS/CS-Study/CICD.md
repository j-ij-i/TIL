# CI/CD

![cicd](https://user-images.githubusercontent.com/46212602/178281056-b396853c-7203-4ad5-a987-6d10a915961b.png)

- 애플리케이션 개발 단계를 자동화해 보다 짧은 주기로 통합 및 배포하는 것을 의미
- 인터그레이션 헬(Integration Hell)을 해결하기 위한 솔루션으로 지속적인 통합, 지속적인 서비스 제공, 지속적인 배포가 핵심

## CI: Continuous Integration - 지속적인 통합

- 새로운 코드 변경 사항이 정기적으로 빌드 및 테스트를 거쳐 공유 리포지토리에 통합되는 것을 의미
- 여러 개발자가 동시에 작업하며 발생할 수 있는 충돌 문제를 수시로 확인하고 해결할 수 있다.
- 버그를 빠르게 찾아 해결하고, 소프트웨어 품질을 개선하며, 새로운 업데이트 테스트와 출시 시간을 단축 시킬 수 있다.
- EX) 특정 날에 머지하기로 할 경우, 여러 개발자가 작업한 내용이 크게 충돌할 수 있습니다. 따라서 CI를 통해 코드 변경 사항을 공유 브랜치 또는 트랭크로 머지를 자주 수행합니다. 변경 사항이 머지되면, 자동화 테스트를 통해 애플리케이션에 반영되었는지 확인할 수 있습니다. 테스트 수행 후 문제가 발생하면 수정하고, 아니라면 통합합니다. 이 과정은 보통 젠키스와 같은 툴을 사용해 진행됩니다.

## CD: Continuous Delivery(&Deployment) - 지속적인 배포

- 개발자의 변경 사항을 리포지토리에서 고객의 프로덕션 환경까지 자동으로 배포
- EX) 프로덕션 준비가 완료된 빌드를 코드 리포지토리에 자동으로 배포합니다. 테스트 자동화가 되어야 있어야 가능하며, 실제 사례에서는 개발자가 애플리케이션 변경 사항을 작성한 이후 몇 분 이내에 테스트를 통과하고 반영되는 것을 의미합니다.

---

### 참고 링크

[https://walkingplow.tistory.com/78#:~:text=CI%2FCD는 애플리케이션 개발,지속적인 배포가 핵심입니다](https://walkingplow.tistory.com/78#:~:text=CI%2FCD%EB%8A%94%20%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98%20%EA%B0%9C%EB%B0%9C,%EC%A7%80%EC%86%8D%EC%A0%81%EC%9D%B8%20%EB%B0%B0%ED%8F%AC%EA%B0%80%20%ED%95%B5%EC%8B%AC%EC%9E%85%EB%8B%88%EB%8B%A4) ✨

[https://tecoble.techcourse.co.kr/post/2021-08-14-ci-cd/](https://tecoble.techcourse.co.kr/post/2021-08-14-ci-cd/)

[https://velog.io/@lovi0714/CICD에-대해-알아보자](https://velog.io/@lovi0714/CICD%EC%97%90-%EB%8C%80%ED%95%B4-%EC%95%8C%EC%95%84%EB%B3%B4%EC%9E%90)

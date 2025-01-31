# 🛠 실무에 바로 적용하는 프론트엔드 테스트
~~~ plaintext
💡  "실무에 바로 적용하는 프론트엔드 테스트 강의" 내용을 정리한 레포지토리입니다.  
    주요 내용, 실습 코드 및 테스트 관련 개념을 기록했습니다.
~~~

## 📚 목차
- [📝 개요](#개요)
- [🚀 테스트 코드의 중요성](#테스트-코드의-중요성)
- [🛠 테스트 코드 작성 규칙](#테스트-코드-작성-규칙)
- [🧩 단위 테스트란](#단위-테스트란)
- [🔗 통합 테스트란](#통합-테스트란)

---

## 📝 개요
- **다루는 내용**:
  - 프론트엔드 테스트의 핵심 원리
  - 실무에서 바로 활용 가능한 테스트 구현 방법
  - 다양한 실습 예제 및 시나리오
- **테스트 유형**:
  - 단위 테스트(Unit Testing)
  - 통합 테스트(Integration Testing)
- **테스트 프레임워크**: `Vitest`
- **사용 도구**: Testing Library, MSW 등

---

## 🚀 테스트 코드의 중요성
✅ **좋은 설계에 대한 사고를 도와준다**  
   - 테스트 코드를 위해 **결합도를 낮춘 설계**를 하게 되므로, **자연스럽게 더 좋은 설계**로 이어짐.  

✅ **테스트 코드를 기반으로 안정적으로 리팩토링 가능**  
   - 작은 범위로 개발을 진행하면서 문제를 빠르게 발견하고 수정 가능.  

✅ **좋은 테스트 코드는 애플리케이션의 이해를 돕는 문서 역할**  
   - `describe`만으로 **구동 방식을 이해**할 수 있도록 테스트를 설계하자.

---

## 🛠 테스트 코드 작성 규칙
📌 **인터페이스를 기준으로 테스트 작성하기**  
   - 내부 구현에 대한 테스트는 **강한 의존성** 때문에 깨지기 쉬우므로, **외부 인터페이스 중심으로 테스트**해야 유지보수가 쉬움.  

📌 **100% 커버리지보다는 의미 있는 테스트를 고민하기**  
   - **커버리지를 목표로 하는 테스트**는 오히려 유지보수 비용이 커질 수 있음.  
   - **"이 테스트가 정말 필요한가?"**를 항상 고민하기.  

📌 **테스트 코드도 유지보수 대상! 가독성을 높이자**  
   - 테스트 전, **테스트의 목적을 명확하게 작성**하기.  
   - 하나의 테스트에는 **가급적 하나의 동작만 검증**하기.

---

## 🧩 단위 테스트란?
> 단일 함수의 결괏값 또는 단일 컴포넌트(클래스)의 **상태(UI)나 행위**를 검증하는 테스트

### ❕ 단위 테스트 코드 작성 시 체크리스트
- ✅ **상세한 테스트 디스크립션을 작성해 가독성을 높이기**
- ✅ **내부 DOM 구조나 로직에 영향을 받지 않는 테스트 작성**
- ✅ **최종 렌더링 결과물(DOM 구조)이 올바르게 변경되는지 검증**

### ✅ 단위 테스트 대상 선정 기준
📌 **state나 로직 처리 없이 UI만 그리는 컴포넌트는 검증하지 않는다**  
   → 해당 검증은 **Storybook과 같은 도구를 사용**하여 검증.  

📌 **간단한 로직을 처리하는 컴포넌트는 상위 컴포넌트의 통합 테스트에서 검증**  

📌 **공통 유틸 함수는 단위 테스트로 검증한다**  
   → **독립적인 로직**이므로 개별적으로 검증이 필요.  

### 📌 **자세한 강의 내용은 아래 문서를 참고**
- [테스트 환경과 매처(Matcher) 상세 보기](./unit-test/docs/test-environment-and-matchers.md)<br>
- [Setup과 Teardown 상세 보기](./unit-test/docs/setup-and-teardown.md)<br>
- [React Testing Library와 컴포넌트 테스트](./unit-test/docs/react-testing-library-and-component-test.md)<br>
- [모듈 모킹(Mock)](./unit-test/docs/module-mocking.md)<br>
- [리액트 훅 테스트(feat. act함수)](./unit-test/docs/react-hook-test.md)<br>
- [타이머와 비동기 테스트](./unit-test/docs/timer-and-async-test.md)<br>
- [userEvent를 사용한 사용자 상호작용 테스트](./unit-test/docs/userEvent-Interaction-Testing.md)<br>
---

## 🔗 통합 테스트란?
> 여러 개의 모듈, 컴포넌트 또는 API가 **정상적으로 상호작용하는지 검증하는 테스트**.

✅ **단위 테스트와의 차이점**
- 단위 테스트는 **각 개별 요소를 검증**하는 반면,  
  **통합 테스트는 여러 요소가 올바르게 연동되는지 검증**.

✅ **테스트 방식**
- API와의 상호작용을 확인하기 위해 **MSW(Mock Service Worker)** 사용.
- `setupTests.js`에서 **글로벌 설정**을 적용.

---

## 🎯 마무리
이 문서는 **프론트엔드 테스트의 개념과 실무 적용 방법을 정리**한 레포지토리입니다.  
추가적으로 궁금한 점이나 개선할 사항이 있다면 **PR을 환영합니다!** 🚀

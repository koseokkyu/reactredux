Redux는 JavaScript 앱을위한 예측 가능한 컨테이너입니다.
(WordPress 프레임 워크를 찾고 있다면 Redux Framework를 확인하십시오 .)

일관성있게 작동하고 다양한 환경 (클라이언트, 서버 및 기본)에서 실행되며 테스트하기 쉬운 응용 프로그램을 작성할 수 있습니다. 또한 실시간 디버거와 함께 실시간 코드 편집과 같은 훌륭한 개발자 경험을 제공합니다 .

Redux를 React 와 함께 사용 하거나 다른 뷰 라이브러리와 함께 사용할 수 있습니다 .

Redux는 JavaScript app을 위한 상태 관리, 데이터 관리 라이브러리이다. React에 종속적인 것은 아니며 다른 View 라이브러리들과도 얼마든지 함께 사용 가능하다. (ex. Vue.js 등)
react 로 만든 app에 적용하려면 react-redux 라이브러리의 도움을 받으면 좀 더 편하게 적용이 가능하다.

Redux에 대해 이해하려면 먼저 Flux에 대한 이해가 필요하다.


Flux는 Facebook에서 제안한 아키텍쳐인데, MVC와 비슷하면서 다른 점을 가지고 있다.

전통적인 MVC 패턴에서는 Model, View, Controller가 구성 요소이다. Flux는 Action, Dispatcher, Store, View로 구성되어 있다.
MVC에 대해 알고 있는 사람을 위해 단순하게 설명하자면 Store가 모델, View는 그대로 View, Action과 Dispatcher가 Controller의 역할을 한다고 말할 수 있지만.. 똑같다면 Flux를 새롭게 말할 이유가 없다.
Flux에서는 흐름이 한 방향으로만 흐른다고 이야기한다. View가 Store를 직접 변경하는 일은 없다는 이야기이다. Store의 모든 변화는 Action에서부터 기인하고, Store가 변경되면 View를 다시 그린다. 만약 View에서 Store의 변경이 필요하면 Action을 날리고, 그 Action이 Store를 변경하도록 한다.
여기까지 이야기해도 MVC와 별다른 게 없다고 느낄 수 있다. Controller가 Model을 바꾸고.. View가 업데이트 되고.. 하지만 Flux에서는 View가 Model을 바꾸는 방법을 바꿈으로써 View - Model 간의 순환고리를 끊어냈다. 시스템에서는 Action들을 받아서 처리하되, 한번에 모든 변경을 처리할 필요가 없어진다는 것이다. 이렇게 함으로써 역할을 단순화 시키고 반복적인 함수 호출을 피해 성능의 향상을 가져올 수 있게 된다.

Redux는 Flux의 개념을 구현한 라이브러리라고 할 수 있다. 같지는 않지만 Flux의 아이디어로부터 출발한 것으로 보인다. 다만 Redux에서는 단 하나의 전역적인 Store만을 사용한다는 점이 다르다.
진실은 하나의 소스로부터
Redux에서 말하는 세 가지 원칙이 있다. 이 중 첫번째가 방금 전에 이야기한, 단 하나의 전역적인 Store를 사용한다는 것이다. 어플리케이션 전체에서 사용하는 전역적인 Store를 사용함으로써 어플리케이션의 현재 상태를 snapshot으로 저장할 수도 있고, 실행취소/다시실행 등의 구현도 간단해진다고 말하고 있다.
상태는 읽기 전용이다
Redux의 Store는 읽기 전용이다. Store를 바꾸는 방법은 오직 Action을 통해서만 가능하다. 차후에 다룰 Reducer라는 함수가 Store를 어떻게 바꾸는지를 정의하고 그 외에는 Store를 변경할 수 없고 읽기만 해야 한다. 이를 통해 다른 곳(예를 들면 REST API 호출이나 View event)에서 Store를 함부로 변경할 수 없다는 것을 보장받을 수 있다.
변화는 순수 함수로 작성되어야 한다
위에서 말한 Reducer에 대한 내용이다. Reducer는 단순히 현재 상태와 Action을 전달받고 새로운 상태를 반환하는 JS 함수이다. Action을 받아서 이 Action에 따라서 Store가 어떻게 바뀌는지를 나타낸다. Store에 직접 접근해서 변경하는 것이 아니라 새로운 상태를 반환한다는 점에 유의해야 한다. Store는 읽기 전용이다.

[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat)](http://standardjs.com/)

For beginners like me to learn the concepts in [Redux](https://github.com/reactjs/redux)

To run this example:

1. [Download this repo](https://github.com/jackielii/simplest-redux-example/archive/master.zip) or `git clone https://github.com/jackielii/simplest-redux-example.git`
2. From the repo folder run:  
   `npm install`
3. `npm start`
4. open [http://localhost:8000/](http://localhost:8000/) in the browser

And also head over to http://redux.js.org/ for some great documentation.

There is also a [webpack](https://github.com/jackielii/simplest-redux-example/tree/webpack) and an [ES5](https://github.com/jackielii/simplest-redux-example/tree/es5) example.



이 프로젝트는 [hello world](http://d2.naver.com/helloworld) 공개한 React 개발 가이드에 필요한 샘플 코드입니다.

`create-react-app`을 사용하여 만들어져 있으며 `npm install` 후 `npm start`을 사용하여 실행할 수 있습니다.

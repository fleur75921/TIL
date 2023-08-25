고급 자바스크립트 프로젝트나 리액트 프로젝트는<br>
여러 파일에 코드를 분리해 관리하기 쉽게 만드는 것이 좋다.<br>
이를 위해서 import와 export 구문이 사용된다.

## 1. import / export

<br>

    [util.js]
    export let apiKey = "asdasdaghlkl";

    [app.js]
    import { apiKey } from "./util.js"
    경로는 같은 폴더인 경우 ./ 상위 폴더인 경우 ../ 과 같다.
    확장자 .js를 생략해도 빌드 프로세스에서 자동으로 추가된다.

import와 export를 사용하더라도 결과물의 소스 코드를 보면 type="module"이 없는 것을 확인할 수 있는데

이는 빠른 전송을 위해 빌드 프로세스에서 파일을 하나로 합치기 때문이다.

<br>

## 2. default

<br>

    [util.js]
    export default "asdasdaghlkl";
    export let key = "bkalqol;"

    [app.js]
    import apiKey from "./util.js"
    import { key as apple } from "./util.js"

export시에 default를 사용하면 항상 하나의 함수 혹은 하나의 값을 내보낼 수 있다.<br>
이를 import할 때는 중괄호가 필요하지 않으며 원하는 이름을 지정해야 한다.<br>
default가 아닌 경우에도 as를 이용해 원하는 이름을 지정할 수 있다.

<br>

## 3. 객체 import

    [util.js]
    export default "asdasdaghlkl";
    export let key = "bkalqol;"

    [app.js]
    import * as util from "./util.js"
    console.log(util.key) // bkalqol

import하려는 모든 대상의 이름을 쓰는 대신에 \*로 표시하면서 as로 이름을 지정해
하나의 객체로 파일을 가져올 수도 있다. 이 때는 점 표기법(.)을 사용해<br>
값이나 함수에 접근할 수 있다.<br>
default의 경우 default라는 이름으로 접근한다.

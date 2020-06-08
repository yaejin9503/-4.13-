
<b>const</b>

- 한번 선언하고 바뀌지 않는 값 

<b>let</b> 

- 바뀌게 될 수 있는 값 (기존 javascript의 var과 비슷한 개념이라고 생각하면 됨

<b>let 과 var의 차이점 </b>

- 작동 방식에 있어서 scope 가 다름

<b>var 은 scope 가 함수단위</b>

```
function foo() {
  var a = 'hello';
  if (true) {
    var a = 'bye';
    console.log(a); // bye
  }
  console.log(a); // bye
}
```

<b>반면 const 와 let 은 scope 가 블록 단위</b>
```
function foo() {
  let a = 'hello';
  if (true) {
    let a = 'bye';
    console.log(a); // bye
  }
  console.log(a); // hello
}
```

<b>조건부 렌더링 </b>
```
JSX 내부에서 조건부 렌더링을 할 때는 보통 삼항 연산자를 사용하거나, AND 연산자를 사용한다. 
반면에 if문을 사용할 수는 없다 (사용하려면 IIFE(즉시 실행 함수 표현)을 사용해야한다.)
```

```
import React, { Component } from 'react';

class App extends Component {
  render() {
    return (
      <div>
        {
          1 + 1 === 2 
            ? (<div>맞아요!</div>)
            : (<div>틀려요!</div>)
        }
      </div>
    );
  }
}

export default App;
```

이렇게 되면 화면에는 맞아요! 가 출력되고, 3으로 바꾸면 틀려요!가 출력된다. 

<b>AND 연산자</b> 

- 삼항연산자는 true일때와 false 일 때 다른 것들을 보여주고 싶을 때 사용하는 반면, AND 연산자의 경우 단순히 우리의 
조건이 true 일 때만 보여주고 false 일 경우 아무것도 보여주고 싶지 않을 때 사용한다. 
```
import React, { Component } from 'react';

class App extends Component {
  render() {
    return (
      <div>
        {
          1 + 1 === 2 && (<div>맞아요!</div>)
        }
      </div>
    );
  }
}

export default App;

<b>조금 복잡한 조건을 작성해야 할 때</b>

- JSX 밖에서 로직을 작성하는 것이 좋지만 
- JSX 내부에서 작성해야 한다면, 이렇게 IIFE를 사용한다. 
```
import React, { Component } from 'react';

class App extends Component {
  render() {
    const value = 1;
    return (
      <div>
        {
          (function() {
            if (value === 1) return (<div>하나</div>);
            if (value === 2) return (<div>둘</div>);
            if (value === 3) return (<div>셋</div>);
          })()
        }
      </div>
    );
  }
}

export default App;
```

<b>style 과 className</b>
```
import React, { Component } from 'react';

class App extends Component {
  render() {
    const style = {
      backgroundColor: 'black',
      padding: '16px',
      color: 'white',
      fontSize: '12px'
    };

    return (
      <div style={style}>
        hi there
      </div>
    );
  }
}

export default App;
```

```
.App {
  background: black;
  color: aqua;
  font-size: 36px;
  padding: 1rem;
  font-weight: 600;
}

App.css 파일을 열어서 다음과 같이 수정
```

```
import React, { Component } from 'react';
import './App.css'

class App extends Component {
  render() {
    return (
      <div className="App">
        리액트
      </div>
    );
  }
}

export default App;
```



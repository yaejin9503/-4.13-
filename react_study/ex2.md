```
import React, { Component } from 'react';

const MyName = ({name}) => {
    return (
    <div>
        안녕하세요 ! 제 이름은 {name}  입니다.        
    </div>
    );
};

export default MyName;

/*함수형 컴포넌트와 클래스형 컴포넌트의 주요 차이점은, 
state, LifeCycle이 빠져있다는 점. 
그래서, 컴퓨넌트 초기 마운트가 아주 미세하게 빠르고, 
메모리 자원을 덜 사용한다. 
미세한 차이라, 컴포넌트를 무수히 많이 렌더링 하게 되는게 
아니라면 성능적으로 큰 차이는 없다. 
*/
```


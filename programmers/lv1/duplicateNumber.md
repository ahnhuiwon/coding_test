## `2016년`

### 문제 설명

정수가 담긴 배열 array와 정수 n이 매개변수로 주어질 때, array에 n이 몇 개 있는 지를 return 하도록 solution 함수를 완성해보세요.

<br />

### 제한 조건

- 1 ≤ array의 길이 ≤ 100
- 0 ≤ array의 원소 ≤ 1,000
- 0 ≤ n ≤ 1,000

<br />

### 입출력 예

|array|n|result|
|------|---|---|
|[1,1,2,3,4,5]|1|2|
|[0,2,3,4]|1|0|

<br />

### 테스트 통과 코드

```

/**
 * Queue 객체
 *
 */
class AbstractQueue {
    constructor(identifier) {
        this.identifier = identifier;
        this.queueArray = [];
    }

    pushItem(item) {
		this.queueArray.push(item);
	}

	shiftItem() {
		return this.queueArray.shift();
	}

	popItem() {
		return this.queueArray.pop();
	}

	unshiftItem(item) {
		this.queueArray.unshift(item);
	}

	getLength() {
		return this.queueArray.length;
	}
        
	displayData() {
		return this.queueArray;
	}
    
}


/**
 *
 * 문제 풀이 함수
 *
 */
function solution(array, n) {
    
    const numberQueue = new AbstractQueue("duplicateNumbers");
    const agreementArray = [];
    

    /**
     *
     * 매개변수 array(배열)의 길이만큼
     * 반복해서 Queue 자료구조에 넣어줍니다.
     *
     */
    array.map( data => numberQueue.pushItem( data ) );
    

    /**
     *
     * Queue 자료구조에 들어있던 데이터를 배출해
     * 매개변수 n(숫자)와 비교해 일치하는 데이터를 배열에 넣습니다.
     *
     */
    for(let i = 0; i < numberQueue.queueArray.length; i++) {

        const shiftElement = numberQueue.shiftItem();

        if( shiftElement === n ) {
            agreementArray.push( elements );
        }
    }
    
    return agreementArray.length;
    
}
```

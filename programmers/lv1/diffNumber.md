## `같은 숫자는 싫어`

### 문제 설명

배열 arr가 주어집니다. 배열 arr의 각 원소는 숫자 0부터 9까지로 이루어져 있습니다.
이때, 배열 arr에서 연속적으로 나타나는 숫자는 하나만 남기고 전부 제거하려고 합니다. 
단, 제거된 후 남은 수들을 반환할 때는 배열 arr의 원소들의 순서를 유지해야 합니다. 예를 들면,

- arr = [1, 1, 3, 3, 0, 1, 1] 이면 [1, 3, 0, 1] 을 return 합니다.
- arr = [4, 4, 4, 3, 3] 이면 [4, 3] 을 return 합니다.

배열 arr에서 연속적으로 나타나는 숫자는 제거하고 남은 수들을 return 하는 solution 함수를 완성해 주세요.

<br />

### 제한 조건

- 배열 arr의 크기 : 1,000,000 이하의 자연수
- 배열 arr의 원소의 크기 : 0보다 크거나 같고 9보다 작거나 같은 정수

<br />

### 입출력 예

|array|result|
|------|---|
|[1,1,3,3,0,1,1]|[1,3,0,1]|
|[4,4,4,3,3]|[4,3]|

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
function solution(arr) {
    
    // 매개변수 arr을 담는 Queue 자료구조 객체
    const numberQueue = new AbstractQueue("numberQueue");
    // 다른 숫자를 담는 Queue 자료구조 객체
    const diffNumberQueue = new AbstractQueue("diffNumberQueue");
    

    /**
     *
     * 매개변수 arr(배열)의 길이만큼
     * 반복해서 Queue 자료구조에 삽입합니다.
     *
     */
    for(let i = 0; i < arr.length; i++) {
        numberQueue.pushItem( arr[i] );
    }

    const queueCount = numberQueue.getLength();
    
    /**
     *
     * Queue 자료구조에 들어있던 데이터를 배출해
     * diffNumberQueue의 마지막 요소와 비교하여 다른 숫자라면
     * 데이터를 삽입합니다.
     *
     */
    for(let j = 0; j < queueCount; j++) {
        
        const diffQueueLength = diffNumberQueue.getLength();
        const ejectionData = numberQueue.shiftItem();
        
        if( ( diffQueueLength === 0 ) || ( diffNumberQueue.queueArray[diffQueueLength - 1] !== ejectionData ) ) {
            diffNumberQueue.pushItem( ejectionData );
        }
    }
    
    return diffNumberQueue.queueArray;
    
}
```

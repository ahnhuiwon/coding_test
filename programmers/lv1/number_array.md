## `나누어 떨어지는 숫자 배열`

### 문제 설명

array의 각 element 중 divisor로 나누어 떨어지는 값을

오름차순으로 정렬한 배열을 반환하는 함수, solution을 작성해주세요.

divisor로 나누어 떨어지는 element가 하나도 없다면 배열에 -1을 담아 반환하세요.

<br />

### 제한 조건

- arr은 자연수를 담은 배열입니다.
- 정수 i, j에 대해 i ≠ j 이면 arr[i] ≠ arr[j] 입니다.
- divisor는 자연수입니다.
- array는 길이 1 이상인 배열입니다.



<br />

### 입출력 예

|arr|division|return|
|---|---|---|
|[5, 9, 7, 10]|5|[5, 10]|
|[2, 36, 1, 3]|1|[1, 2, 3, 36]|
|[3,2,6]|10|[-1]|

<br />

### 테스트 통과 코드 및 해설

```
function solution(arr, divisor) {
    var answer = [];
    
    // arr의 길이 만큼 반복합니다.
    for(let i=0; i<arr.length; i++) {
    
        // arr[i]가 divisor 나누는 값이 0일때
        if(arr[i] % divisor == 0) {
            answer.push(arr[i]);
        }
    }
    
    // answer의 길이가 0이 아니라면 answer의 요소들을 정렬합니다.
    return answer.length != 0 ? answer.sort((a,b) => a-b) : [-1];
}
```

<br />

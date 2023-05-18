## `자릿수 더하기`

### 문제 설명

자연수 N이 주어지면,

N의 각 자릿수의 합을 구해서 return 하는 solution 함수를 만들어 주세요.

예를들어 N = 123이면 1 + 2 + 3 = 6을 return 하면 됩니다.

<br />

### 제한 조건

- N의 범위 : 100,000,000 이하의 자연수

<br />

### 입출력 예

|N|answer|
|---|---|
|123|6|
|987|24|

<br />

### 테스트 통과 코드 및 해설

```
function solution(n) {
    var answer = 0;


    // 매개변수를 문자열로 변경합니다
    const convert_str = n.toString();
    
    
    // 변경한 문자열을 반복해 숫자로 변경하고 answer에 값을 더해줍니다.
    let i=0;
    while(i<convert_str.length) {
        answer += Number(convert_str[i])
        i++;
    }

    return answer;
}
```

<br />

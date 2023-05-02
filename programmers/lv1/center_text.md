## `가운데 글자 가져오기`

### 문제 설명

단어 s의 가운데 글자를 반환하는 함수,

solution을 만들어 보세요. 단어의 길이가 짝수라면 가운데 두글자를 반환하면 됩니다.

<br />

### 제한 조건

- s는 길이가 1 이상, 100이하인 스트링입니다.

<br />

### 입출력 예

|s|return|
|---|---|
|"abcde"|"c"|
|"qwer"|"we"|

<br />

### 테스트 통과 코드 및 해설

```
function solution(s) {
    var answer = '';
    
    // 파라미터 s의 반 값을 구하고 반올림합니다.
    var string_count = Math.floor(s.length / 2) ;
    
    
    // 짝수 일때
    if(s.length % 2 === 0) {
        const first_length = s[string_count - 1];
        const second_length = s[string_count];
        
        answer = first_length + second_length;
    } else {
    
        // 홀수 일때
        answer = s[string_count];
    }
    
    
    return answer;
}
```

<br />

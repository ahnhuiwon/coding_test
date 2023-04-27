## `이상한 문자 만들기`

### 문제 설명

2문자열 s는 한 개 이상의 단어로 구성되어 있습니다. 

각 단어는 하나 이상의 공백문자로 구분되어 있습니다. 

각 단어의 짝수번째 알파벳은 대문자로, 홀수번째 알파벳은 소문자로 바꾼 문자열을 리턴하는 함수, 

solution을 완성하세요.

<br />

### 제한 조건

- 문자열 전체의 짝/홀수 인덱스가 아니라, 단어(공백을 기준)별로 짝/홀수 인덱스를 판단해야합니다.
- 첫 번째 글자는 0번째 인덱스로 보아 짝수번째 알파벳으로 처리해야 합니다.

<br />

### 입출력 예

|s|return|
|---|---|
|"try hello world"|"TrY HeLlO WoRlD"|

<br />

### 테스트 통과 코드

```
function solution(s) {
    var answer = '';
    var count = 0;
    
    for(let i=0; i < s.length; i++) {
        if(s[i] != ' ') {
            if(count % 2 == 0) {
                answer += s[i].toUpperCase();
            }
            if(count % 2 != 0) {
                answer += s[i].toLowerCase();
            }
            
            count++;
        } else {
            answer += ' '
            count = 0;
        }
    }

    
    
    return answer;
}
```

<br />

**해설**

 - 파라미터로 받아온 문자열 데이터 s의 길이만큼 반복합니다.
 - s[i] 데이터가 띄어쓰기(공백)이 아닐 경우 다음 조건문을 실행합니다. 
 - count 데이터가 짝수라면 대문자, 홀수라면 소문자로 변환을 한 뒤 count를 증가합니다.
 - s[i] 데이터가 띄어쓰기(공백)일 경우 띄어쓰기를 answer에 += 한 뒤 count를 다시 0으로 돌립니다.

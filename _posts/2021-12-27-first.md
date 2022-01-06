---
layout: single
title: "Programmers_1 : 완주하지 못한 선수"
---


# ```sort()``` 를 이용한 두 배열 비교하기.



**문제 설명**

수많은 마라톤 선수들이 마라톤에 참여하였습니다. 단 한 명의 선수를 제외하고는 모든 선수가 마라톤을 완주하였습니다.

마라톤에 참여한 선수들의 이름이 담긴 배열 participant와 완주한 선수들의 이름이 담긴 배열 completion이 주어질 때, 완주하지 못한 선수의 이름을 return 하도록 solution 함수를 작성해주세요.

##### **제한사항**

- 마라톤 경기에 참여한 선수의 수는 1명 이상 100,000명 이하입니다.
- completion의 길이는 participant의 길이보다 1 작습니다.
- 참가자의 이름은 1개 이상 20개 이하의 알파벳 소문자로 이루어져 있습니다.
- 참가자 중에는 동명이인이 있을 수 있습니다.



**어려웠던 부분**

* 동명이인이 있을 수 있다.
* 두 배열을 어떻게 비교 할 것인가.



**풀이**

```javascript
function solution(participant, completion) {
    
    var answer = '';
    
    participant.sort();
    completion.sort();

    for(let i=0; i<participant.length; i++){
        if(participant[i] != completion[i]){
            answer = participant[i]
            break;
        }
    }

   
    return answer;
}
```



---

1. 먼저 참가자 배열(participant)과, 완주자 배열(completion) 을 sort()라는 메소드를 사용하여 같은 기준으로 정렬시켜 주었다.
2. 같은 기준으로 배열을 정렬시켰기 때문에, 뒤죽박죽의 순서로 있던 배열이 같은 순서로 이름들이 나열되어 있는 두개의 배열로 바뀌었다.
3. 이렇게 되면, 참가자 수 만큼 하나씩 돌아가며 배열을 비교해 보았을때
4. 다른 이름이 나온다면? 그 이름이 바로 완주자 명단에는 없지만, 참가자 명단에는 있는 이름이 된다.

---



**배운것**

```javascript
Array.sort()
```

문자열의 유니코드 코드 포인트를 따라 새로운 배열로 반환한다. 

여기서 새로운 배열 이란, 복사 되는 것이 아닌 기존의 배열을 변환 시키는 것 이기 때문에 조심해야 한다.

```javascript
const array = ['apple', 'orange', 'banana']
array.sort() // [ 'apple', 'banana', 'orange' ]

const numbers = [1, 56, 47, 91]
numbers.sort() // [ 1, 47, 56, 91 ]
```




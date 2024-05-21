미들러 | 자바
# 📞 해시 | [전화번호 목록](https://school.programmers.co.kr/learn/courses/30/lessons/42577)

## 문제 설명
전화번호부에 적힌 전화번호 중, 한 번호가 다른 번호의 접두어인 경우가 있는지 확인하려 합니다.  
전화번호가 다음과 같을 경우, 구조대 전화번호는 영석이의 전화번호의 접두사입니다.
<br>
- 구조대 : 119
- 박준영 : 97 674 223
- 지영석 : 11 9552 4421
<br>
전화번호부에 적힌 전화번호를 담은 배열 phone_book 이 solution 함수의 매개변수로 주어질 때, 어떤 번호가 다른 번호의 접두어인 경우가 있으면 false를 그렇지 않으면 true를 return 하도록 solution 함수를 작성해주세요.

## 제한 사항
- phone_book의 길이는 1 이상 1,000,000 이하입니다.
  - 각 전화번호의 길이는 1 이상 20 이하입니다.
  - 같은 전화번호가 중복해서 들어있지 않습니다.

## 입출력 예제
| **phone_book**                    | **return** |
|-----------------------------------|------------|
| ["119", "97674223", "1195524421"] | false      |
| ["123","456","789"]               | true       |
| ["12","123","1235","567","88"]    | false      |


## 입출력 예 설명
**입출력 예 #1**  
앞에서 설명한 예와 같습니다.

**입출력 예 #2**  
한 번호가 다른 번호의 접두사인 경우가 없으므로, 답은 true입니다.  

**입출력 예 #3**  
첫 번째 전화번호, “12”가 두 번째 전화번호 “123”의 접두사입니다. 따라서 답은 false입니다.

### 알림

2021년 3월 4일, 테스트 케이스가 변경되었습니다. 이로 인해 이전에 통과하던 코드가 더 이상 통과하지 않을 수 있습니다.

---
## Solution with Array and `.startsWith()` and `.compareTo()`
```java
import java.util.Arrays;

class Solution {
    public boolean solution(String[] phone_book) {
        boolean answer = true;
        Arrays.sort(phone_book);
        
        for (int i = 0; i < phone_book.length - 1; i++) {
            for (int j = i + 1; j < phone_book.length; j++) {
                if (phone_book[j].startsWith(phone_book[i])){
                    return false;
                }else if(phone_book[j].substring(0).compareTo(phone_book[i].substring(0)) != 0){
                    break;
                }
                
            }
        }
        return answer;
    }
}
```
<details>
  <summary>채점 결과</summary>

  ![채점 결과](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/bb936a3b-1f3c-4125-a4e8-e04e6c1339ca)
</details>

---

#### 참고 자료
[[Java]특정 문자열로 시작하는지 확인하는 방법](https://developer-talk.tistory.com/405)  
[Java - 배열 정렬(Sorting) (오름차순, 내림차순)](https://codechacha.com/ko/java-sorting-array/)  
[Java - 문자열(String)을 비교하는 방법 (==, equals, compare)](https://codechacha.com/ko/java-string-compare/)  
[[Java] .length, .length(), .size()](https://developer-rooney.tistory.com/132)  
[[ Java ] 자바 반복문의 continue 와 break](https://mjn5027.tistory.com/94)  
[[java] for each문 사용법](https://jink1982.tistory.com/140)  
[[JAVA] 문자열 자르기 ( indexOf()/ substring() / split() )](https://jul-liet.tistory.com/203)  
[[Java] 배열 중복 값 제거하기 (Set, Stream)](https://hianna.tistory.com/554)  
[[Java] 문자열에 특정 문자 포함 여부 확인하기 - contains, indexOf, matches](https://hianna.tistory.com/539)  
[☕ JAVA 배열(Array) 완벽 다루기 가이드](https://inpa.tistory.com/entry/JAVA-%E2%98%95-%EC%9E%90%EB%B0%94-%EB%B0%B0%EC%97%B4Array-%EB%AC%B8%EB%B2%95-%EC%9D%91%EC%9A%A9-%EC%B4%9D%EC%A0%95%EB%A6%AC)  
[[JAVA] 자바 임포트(import)란](https://mozi.tistory.com/549)

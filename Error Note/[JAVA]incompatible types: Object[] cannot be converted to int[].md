# [JAVA]incompatible types: Object[] cannot be converted to int[]

## 에러난 코드
```java
import java.util.*;

public class Solution {
    public int[] solution(int []arr) {
        int[] answer = {};
        int prev = -1;
        Stack<Integer> stack = new Stack<>();
        
        for (int num : arr) {
            if (num != prev) {
                stack.push(num);
            }
            prev = num;
        }
        
        answer = stack.toArray();
        return answer;
    }
}
```
### 실행 결과
```
/Solution.java:16: error: incompatible types: Object[] cannot be converted to int[]
        answer = stack.toArray();
                              ^
1 error
```


## 🔎 에러 해석하기
- incompatible type : 호환되지 않는 type
- Object[] cannot be converted to int[] : int[] 타입의 answer 변수에 Object[] 타입 값을 넣을 수 없다는 말인 것 같다.
  > `스택.toArray()`를 하면 Object[] 타입이 반환되나보다.

## 에러 해결하기💦
- 스택을 int[]배열로 바꾸는 방법
  - 방법1 : for문 사용
    ```java
    int[] answer = new int[스택.size()];

    for(int i = 0; i < 스택.size(); i++) {
        answer[i] = 스택.elementAt(i);
    }
    ```
  - 방법2 : `스택.stream().mapToInt(x -> x).toArray();`
  - 방법3 : `스택.stream().mapToInt(Integer::intValue).toArray();`
  - 방법4 : `스택.stream().filter(x -> x != null).mapToInt(x -> x).toArray();`

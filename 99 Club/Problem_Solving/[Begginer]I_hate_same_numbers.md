<img src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/76b4882b-8e97-408f-a9b2-5b262f2554d7" alt="programmers logo" align="left" width="20%">

**| Java | 스택/큐**

# 🔢 [같은 숫자는 싫어](https://school.programmers.co.kr/learn/courses/30/lessons/12906)😠

## 문제 설명
배열 arr가 주어집니다. 배열 arr의 각 원소는 숫자 0부터 9까지로 이루어져 있습니다.  
이때, 배열 arr에서 연속적으로 나타나는 숫자는 하나만 남기고 전부 제거하려고 합니다.  
단, 제거된 후 남은 수들을 반환할 때는 배열 arr의 원소들의 순서를 유지해야 합니다.  

예를 들면,  
- arr = [1, 1, 3, 3, 0, 1, 1] 이면 [1, 3, 0, 1] 을 return 합니다.  
- arr = [4, 4, 4, 3, 3] 이면 [4, 3] 을 return 합니다.

배열 arr에서 연속적으로 나타나는 숫자는 제거하고 남은 수들을 return 하는 solution 함수를 완성해 주세요.

### 제한사항
- 배열 arr의 크기 : 1,000,000 이하의 자연수
- 배열 arr의 원소의 크기 : 0보다 크거나 같고 9보다 작거나 같은 정수

## 입출력 예

| **arr**         | **answer** |
|-----------------|------------|
| [1,1,3,3,0,1,1] | [1,3,0,1]  |
| [4,4,4,3,3]     | [4,3]      |

## 입출력 예 설명
**입출력 예 #1,2**  
문제의 예시와 같습니다.

---

## ✔ Solution with Stack
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
        
        answer = stack.stream().mapToInt(x -> x).toArray();
        return answer;
    }
}
```
<details>
  <summary>채점 결과</summary>

  ![채점 결과](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/28b8f0df-c7e2-47f4-b13d-02e7dfbb22e9)

</details>
<br>

### 📚 References(참고 자료)
[[JAVA] ArrayList<Integer>를 int[]로 바꾸기](https://velog.io/@coastby/JAVA-ArrayListInteger%EB%A5%BC-int%EB%A1%9C-%EB%B0%94%EA%BE%B8%EA%B8%B0)  
[[ORACLE 문서] java.lang.Object[]](https://docs.oracle.com/javase/7/docs/api/java/util/Vector.html#copyInto(java.lang.Object[]))

---

## ✔ Solution with Array
```java
import java.util.*;

public class Solution {
    public int[] solution(int []arr) {
        int[] answer = new int[arr.length];
        int prev = -1;
        int idx = 0;
        Stack<Integer> stack = new Stack<>();
        
        for (int num : arr) {
            if (num != prev) {
                answer[idx++] = num;
            }
            prev = num;
        }
        
       answer = Arrays.copyOfRange(answer, 0, idx);
        
        return answer;
    }
}
```
<details>
  <summary>채점 결과</summary>

  ![채점 결과](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/9bd386f5-cdcb-4535-99e9-ac92263bafaf)
</details>
<br>

### 📚 Rferences(참고 자료)
[[Java] 특정 인덱스에서 배열 자르기](https://hianna.tistory.com/619)

<img src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/76b4882b-8e97-408f-a9b2-5b262f2554d7" alt="programmers logo" align="left" width="20%">

**|&nbsp;&nbsp;Java&nbsp;&nbsp;|&nbsp;&nbsp;Introductory to coding tests**

# 🆎 **[두 수의 차](https://school.programmers.co.kr/learn/courses/30/lessons/120803)**

🏷 **관련 주제** : `연산자`

<br>

### **문제 설명**

정수 `num1`과 `num2`가 주어질 때, `num1`에서 `num2`를 뺀 값을 return하도록 soltuion 함수를 완성해주세요.

<br>

### **제한사항**
-   \-50000 ≤ `num1` ≤ 50000
-   \-50000 ≤ `num2` ≤ 50000

<br>

### **입출력 예**
| **num1** | **num2** | **result** |
| --- | --- | --- |
| 2 | 3 | \-1 |
| 100 | 2 | 98 |

<br>

### **입출력 예 설명**
**입출력 예 #1**  
`num1`이 2이고 `num2`가 3이므로 2 - 3 = -1을 return합니다.
**입출력 예 #2**  
`num1`이 100이고 `num2`가 2이므로 100 - 2 = 98을 return합니다.

<br>

---

## ✔ Solution with Arithmetic Operators
```java
class Solution {
    public int solution(int num1, int num2) {
        int answer = 0;
        answer = num1 - num2;
        return answer;
    }
}
```
<details>
    <summary>채점 결과</summary>

   ![알고리즘코드카타 인증샷](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/321e6287-851a-46f7-adfc-5883919d95b2)
</details>

#### 📖 연산자 개념 정리([링크🔗](https://github.com/MinjuKang727/Java/blob/main/markdown/Operators(%EC%97%B0%EC%82%B0%EC%9E%90).md))  

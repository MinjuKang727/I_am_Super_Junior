자바 | 챌린저
# 🚚 스택/큐 | 다리를 지나는 트럭

## 문제 설명
트럭 여러 대가 강을 가로지르는 일차선 다리를 정해진 순으로 건너려 합니다.  
모든 트럭이 다리를 건너려면 최소 몇 초가 걸리는지 알아내야 합니다.  
다리에는 트럭이 최대 bridge_length대 올라갈 수 있으며, 다리는 weight 이하까지의 무게를 견딜 수 있습니다.  
단, 다리에 완전히 오르지 않은 트럭의 무게는 무시합니다.

예를 들어, 트럭 2대가 올라갈 수 있고 무게를 10kg까지 견디는 다리가 있습니다.  
무게가 [7, 4, 5, 6]kg인 트럭이 순서대로 최단 시간 안에 다리를 건너려면 다음과 같이 건너야 합니다.

| **경과 시간** | **다리를 지난 트럭** | **다리를 건너는 트럭** | **대기 트럭** |
|---------------|----------------------|------------------------|---------------|
| 0             | []                   | []                     | [7,4,5,6]     |
| 1~2           | []                   | [7]                    | [4,5,6]       |
| 3             | [7]                  | [4]                    | [5,6]         |
| 4             | [7]                  | [4,5]                  | [6]           |
| 5             | [7,4]                | [5]                    | [6]           |
| 6~7           | [7,4,5]              | [6]                    | []            |
| 8             | [7,4,5,6]            | []                     | []            |

따라서, 모든 트럭이 다리를 지나려면 최소 8초가 걸립니다.

solution 함수의 매개변수로 다리에 올라갈 수 있는 트럭 수 bridge_length, 다리가 견딜 수 있는 무게 weight, 트럭 별 무게 truck_weights가 주어집니다.  
이때 모든 트럭이 다리를 건너려면 최소 몇 초가 걸리는지 return 하도록 solution 함수를 완성하세요.

### 제한 조건
- bridge_length는 1 이상 10,000 이하입니다.
- weight는 1 이상 10,000 이하입니다.
- truck_weights의 길이는 1 이상 10,000 이하입니다.
- 모든 트럭의 무게는 1 이상 weight 이하입니다.

## 입출력 예
| **bridge_length** | **weight** | **truck_weights**               | **return** |
|-------------------|------------|---------------------------------|------------|
| 2                 | 10         | [7,4,5,6]                       | 8          |
| 100               | 100        | [10]                            | 101        |
| 100               | 100        | [10,10,10,10,10,10,10,10,10,10] | 110        |

**출처**

※ 공지 - 2020년 4월 06일 테스트케이스가 추가되었습니다.

--- 

# ✔ Solution with Queue
```java
import java.util.LinkedList;
import java.util.Queue;

class Solution {
    // bridge_length : 트럭 최대 대수
    // weight : 다리 최대 하중
    // truck_weights : 트럭 무게 배열
    public int solution(int bridge_length, int weight, int[] truck_weights) {
        Queue<Integer> waiting = new LinkedList();
        
        for (int truck : truck_weights) {
            waiting.offer(truck);
        }
        
        Queue<Integer> OnBridge = new LinkedList();
        int answer = 0;
        int TruckOn = 0;
        int WeightOn = 0;
        
        while(!waiting.isEmpty()) {
            answer++;
            if (!OnBridge.isEmpty() && OnBridge.size() == bridge_length) {
                TruckOn--;
                WeightOn -= OnBridge.poll();
            }
            
            
            if(TruckOn < bridge_length && WeightOn + waiting.peek() <= weight) {
                OnBridge.offer(waiting.peek());
                TruckOn++;
                WeightOn += waiting.poll();
            } else {
                OnBridge.offer(0);
            }
        }
        answer += bridge_length;
        
        return answer;
    }
}
```
<details>
  <summary>채점 결과</summary>

  ![채점 결과](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/f5a59dd5-878d-4702-8c58-8cc0a18ad442)
</details>

---
## 돌아보기
**1️⃣ NullPointerException 발생**
> 조건문에 `큐 != null`로 Queue의 공백 여부를 체크 했더니 Exception 발생
- **`isEmpty()`메서드를 사용하니 Exception 발생하지 않음.**

**2️⃣ 코드 실행 결과값이 정답보다 작게 나옴.**
- `System.out.println();`으로 코드 위치별 값들이 어떻게 되는지 파악
  > while문을 대기 중인 트럭 목록 Queue의 공백 여부로 실행해서 마지막 트럭이 다리에 오르면 바로 While문이 중지하는 것을 발견
  - While문이 끝난 바로 아래에 `결과값 += 다리 길이`코드를 추가해서 해결


---
## References(참고 자료)
[[Java] NullPointException 원인, 예방, 해결하기](https://goddaehee.tistory.com/126)

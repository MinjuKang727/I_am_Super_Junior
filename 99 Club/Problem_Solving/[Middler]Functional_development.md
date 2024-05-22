자바 | 미들러
# ⚙ 스택/큐 | 기능개발

## 문제 설명
프로그래머스 팀에서는 기능 개선 작업을 수행 중입니다. 각 기능은 진도가 100%일 때 서비스에 반영할 수 있습니다.

또, 각 기능의 개발속도는 모두 다르기 때문에 뒤에 있는 기능이 앞에 있는 기능보다 먼저 개발될 수 있고, 이때 뒤에 있는 기능은 앞에 있는 기능이 배포될 때 함께 배포됩니다.

먼저 배포되어야 하는 순서대로 작업의 진도가 적힌 정수 배열 progresses와 각 작업의 개발 속도가 적힌 정수 배열 speeds가 주어질 때 각 배포마다 몇 개의 기능이 배포되는지를 return 하도록 solution 함수를 완성하세요.

### 제한 사항
- 작업의 개수(progresses, speeds배열의 길이)는 100개 이하입니다.
- 작업 진도는 100 미만의 자연수입니다.
- 작업 속도는 100 이하의 자연수입니다.
- 배포는 하루에 한 번만 할 수 있으며, 하루의 끝에 이루어진다고 가정합니다. 예를 들어 진도율이 95%인 작업의 개발 속도가 하루에 4%라면 배포는 2일 뒤에 이루어집니다.
  
## 입출력 예
| **progresses**           | **speeds**         | **return** |
|--------------------------|--------------------|------------|
| [93, 30, 55]             | [1, 30, 5]         | [2, 1]     |
| [95, 90, 99, 99, 80, 99] | [1, 1, 1, 1, 1, 1] | [1, 3, 2]  |

## 입출력 예 설명
**입출력 예 #1**  
첫 번째 기능은 93% 완료되어 있고 하루에 1%씩 작업이 가능하므로 7일간 작업 후 배포가 가능합니다.  
두 번째 기능은 30%가 완료되어 있고 하루에 30%씩 작업이 가능하므로 3일간 작업 후 배포가 가능합니다.  
하지만 이전 첫 번째 기능이 아직 완성된 상태가 아니기 때문에 첫 번째 기능이 배포되는 7일째 배포됩니다.  
세 번째 기능은 55%가 완료되어 있고 하루에 5%씩 작업이 가능하므로 9일간 작업 후 배포가 가능합니다.  

따라서 7일째에 2개의 기능, 9일째에 1개의 기능이 배포됩니다.

**입출력 예 #2**  
모든 기능이 하루에 1%씩 작업이 가능하므로, 작업이 끝나기까지 남은 일수는 각각 5일, 10일, 1일, 1일, 20일, 1일입니다.  
어떤 기능이 먼저 완성되었더라도 앞에 있는 모든 기능이 완성되지 않으면 배포가 불가능합니다.

따라서 5일째에 1개의 기능, 10일째에 3개의 기능, 20일째에 2개의 기능이 배포됩니다.

*※ 공지 - 2020년 7월 14일 테스트케이스가 추가되었습니다.*

---

## ✔ Solution with Stack
```java
import java.util.Stack;

class Solution {
    public int[] solution(int[] progresses, int[] speeds) {
        int[] answer = {};
        Stack<Integer> stack = new Stack<>();
        int release = 0;

        for(int i=0; i < progresses.length; i++) {
            
            if (progresses[i] >= 100) {
                release++;
                continue;
            } else if (release != 0) {
                stack.push(release);
                release = 0; 
            }

            
            while(progresses[i] < 100) {
                for(int j = 0; j < progresses.length; j++) {
                    progresses[j] += speeds[j];
                }
            }

            release++;

        }
        stack.push(release);

        answer = new int[stack.size()];

        for (int i = 0; i < stack.size(); i++) {
            answer[i] = stack.elementAt(i);
        }
        return answer;
    }
}
```
<details>
  <summary>채점 결과</summary>

  ![image](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/7466fcde-4fce-4ad9-be73-a502477a6f5f)
</details>

---

## 돌아보기
### 문제가 발생한 부분
**1️⃣ 코드가 실행은 되는데 답이 틀림**
- **for문 시작부분에 `System.out.println();`을 이용하여 코드 진행이 어떻게 되는지 파악**

<br>

**2️⃣ 결괏값에 배포 개수가 0부터 들어감.**

<details>
  <summary>코드 보기</summary>

  ```java
  import java.util.Stack;
  import java.util.Arrays;
  
  class Solution {
      public int[] solution(int[] progresses, int[] speeds) {
          int[] answer = {};
          Stack<Integer> stack = new Stack<>();
          int release = 0;
  
          System.out.println("i / progresses / release / stack");
          for(int i=0; i < progresses.length; i++) {
              System.out.println(i + " / " + Arrays.toString(progresses) + " / " + release + " / " + stack);
              
              if (progresses[i] >= 100) {
                  release++;
                  continue;
              }
              stack.push(release);
              release = 0; 
              while(progresses[i] < 100) {
                    for(int j = 0; j < progresses.length; j++) {
                        progresses[j] += speeds[j];
                    }
              }
              release++;
          }
  
          answer = new int[stack.size()];
  
          for (int i = 0; i < stack.size(); i++) {
              answer[i] = stack.elementAt(i);
          }
          return answer;
      }
  }
  ```
</details>

<details>
  <summary>코드 실행 결과</summary>

  ![코드 실행 결과](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/dbe3ff8f-d18d-4c26-bcdf-8619d1dfae54)  
</details>

- **Stack에 배포 개수 삽입하는 코드를 if문 안으로 넣어 줌.**

<br>

**3️⃣ 결괏값에 배포 개수가 1개 덜 들어감**  
<details>
  <summary>코드 보기</summary>

  ```java
  import java.util.Stack;
  import java.util.Arrays;
  
  class Solution {
      public int[] solution(int[] progresses, int[] speeds) {
          int[] answer = {};
          Stack<Integer> stack = new Stack<>();
          int release = 0;
  
          System.out.println("i / progresses / release / stack");
          for(int i=0; i < progresses.length; i++) {
              System.out.println(i + " / " + Arrays.toString(progresses) + " / " + release + " / " + stack);
              
              if (progresses[i] >= 100) {
                  release++;
                  continue;
              }else if (release != 0) {
                  stack.push(release);
                  release = 0; 
              }
  
              
              while(progresses[i] < 100) {
                  for(int j = 0; j < progresses.length; j++) {
                      progresses[j] += speeds[j];
                  }
              }
  
              release++;
  
          }
  
          answer = new int[stack.size()];
  
          for (int i = 0; i < stack.size(); i++) {
              answer[i] = stack.elementAt(i);
          }
          return answer;
      }
  }
  ```
</details>

<details>
  <summary>코드 실행 결과</summary>

  ![코드 실행 결과](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/778c01ed-3231-4265-a8a1-bf37f60dc3b9)  
  ***for문을 한바퀴 돈 후에 배포 개수를 삽입하기 때문에 맨 마지막 배포 개수가 안들어 간 것을 확인할 수 있다.***
</details>

- **for문이 끝난 후, 배포 개수를 한번 더 삽입 함.**

<br>

<img src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/f3b9023c-de71-454d-85c3-9b0fbbee24d9" alt="기쁨의 댄스" align="left">

<br><br>

**🎉 코드 실행 성공! 🎉**


# Begginer | [Pokemon](https://school.programmers.co.kr/learn/courses/30/lessons/1845)

## 문제 설명
당신은 폰켓몬을 잡기 위한 오랜 여행 끝에, 홍 박사님의 연구실에 도착했습니다. 홍 박사님은 당신에게 자신의 연구실에 있는 총 N 마리의 폰켓몬 중에서 N/2마리를 가져가도 좋다고 했습니다.
홍 박사님 연구실의 폰켓몬은 종류에 따라 번호를 붙여 구분합니다. 따라서 같은 종류의 폰켓몬은 같은 번호를 가지고 있습니다. 예를 들어 연구실에 총 4마리의 폰켓몬이 있고, 각 폰켓몬의 종류 번호가 [3번, 1번, 2번, 3번]이라면 이는 3번 폰켓몬 두 마리, 1번 폰켓몬 한 마리, 2번 폰켓몬 한 마리가 있음을 나타냅니다. 이때, 4마리의 폰켓몬 중 2마리를 고르는 방법은 다음과 같이 6가지가 있습니다.
<br><br>
  1. 첫 번째(3번), 두 번째(1번) 폰켓몬을 선택  
  2. 첫 번째(3번), 세 번째(2번) 폰켓몬을 선택  
  3. 첫 번째(3번), 네 번째(3번) 폰켓몬을 선택  
  4. 두 번째(1번), 세 번째(2번) 폰켓몬을 선택  
  5. 두 번째(1번), 네 번째(3번) 폰켓몬을 선택  
  6. 세 번째(2번), 네 번째(3번) 폰켓몬을 선택  
<br>
이때, 첫 번째(3번) 폰켓몬과 네 번째(3번) 폰켓몬을 선택하는 방법은 한 종류(3번 폰켓몬 두 마리)의 폰켓몬만 가질 수 있지만, 다른 방법들은 모두 두 종류의 폰켓몬을 가질 수 있습니다. 따라서 위 예시에서 가질 수 있는 폰켓몬 종류 수의 최댓값은 2가 됩니다.
당신은 최대한 다양한 종류의 폰켓몬을 가지길 원하기 때문에, 최대한 많은 종류의 폰켓몬을 포함해서 N/2마리를 선택하려 합니다. N마리 폰켓몬의 종류 번호가 담긴 배열 nums가 매개변수로 주어질 때, N/2마리의 폰켓몬을 선택하는 방법 중, 가장 많은 종류의 폰켓몬을 선택하는 방법을 찾아, 그때의 폰켓몬 종류 번호의 개수를 return 하도록 solution 함수를 완성해주세요.  
<br><br>

## 제한사항
- nums는 폰켓몬의 종류 번호가 담긴 1차원 배열입니다.   
- nums의 길이(N)는 1 이상 10,000 이하의 자연수이며, 항상 짝수로 주어집니다.  
- 폰켓몬의 종류 번호는 1 이상 200,000 이하의 자연수로 나타냅니다.  
- 가장 많은 종류의 폰켓몬을 선택하는 방법이 여러 가지인 경우에도, 선택할 수 있는 폰켓몬 종류 개수의 최댓값 하나만 return 하면 됩니다.  
<br><br>

## 입출력 예
| **nums**      | **result** |
|---------------|------------|
| [3,1,2,3]     | 2          |
| [3,3,3,2,2,4] | 3          |
| [3,3,3,2,2,2] | 2          |


## 입출력 예 설명

**입출력 예 #1**  
문제의 예시와 같습니다.

**입출력 예 #2**  
6마리의 폰켓몬이 있으므로, 3마리의 폰켓몬을 골라야 합니다.  
가장 많은 종류의 폰켓몬을 고르기 위해서는 3번 폰켓몬 한 마리, 2번 폰켓몬 한 마리, 4번 폰켓몬 한 마리를 고르면 되며, 따라서 3을 return 합니다.  

**입출력 예 #3**  
6마리의 폰켓몬이 있으므로, 3마리의 폰켓몬을 골라야 합니다.  
가장 많은 종류의 폰켓몬을 고르기 위해서는 3번 폰켓몬 한 마리와 2번 폰켓몬 두 마리를 고르거나, 혹은 3번 폰켓몬 두 마리와 2번 폰켓몬 한 마리를 고르면 됩니다. 따라서 최대 고를 수 있는 폰켓몬 종류의 수는 2입니다.  

---

## My Solution 1
```java
import java.util.Arrays;

class Solution {
    public int solution(int[] nums) {
        int answer = nums.length/2;
        int typeN = Arrays.stream(nums).distinct().toArray().length;

        return (answer > typeN) ? typeN: answer;
    }
}
```
<details>
  <summary>Accuracy Test Results(정확성 테스트 결과)</summary>
  
  <img alt="sol1_accuracy_test_result" src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/c537a3d9-276a-483c-8bf3-bf6439cc1789">
</details>
<br>

## My Solution 2
```java
import java.util.Arrays;

class Solution {
    public int solution(int[] nums) {
        int answer = nums.length/2;
        int typeN = Arrays.stream(nums).distinct().toArray().length;
        answer = (answer > typeN) ? typeN: answer;
        
        return answer;
    }
}
```
<details>
  <summary>Accuracy Test Results(정확성 테스트 결과)</summary>
  
  <img alt="sol2_accuracy_test_result" src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/6bca0106-1d0a-4906-8fd6-ead44d6f07df">
</details>
<br>

## My Solution 3
```java
import java.util.Arrays;

class Solution {
    public int solution(int[] nums) {
        int answer = nums.length/2;
        int typeN = Arrays.stream(nums).distinct().toArray().length;
        answer = Integer.min(answer, typeN);
        
        return answer;
    }
}
```
<details>
  <summary>Accuracy Test Results(정확성 테스트 결과)</summary>
  
  ![sol3_accuracy test](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/391bfa39-0c2f-469b-bdf6-c3a9c5e7ff3e)
</details>
<br>

## My Solution 4
```java
import java.util.Arrays;

class Solution {
    public int solution(int[] nums) {
        int answer = nums.length/2;
        int typeN = Arrays.stream(nums).distinct().toArray().length;
        if (answer > typeN) return typeN;
        
        return answer;
    }
}
```
<details>
  <summary>Accuracy Test Results(정확성 테스트 결과)</summary>

  ![sol4_accuracy test](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/0414e7bc-622d-4020-94cb-5a9bb9723637)
</details>
<br>

## My Solution 5
```java
import java.util.Arrays;

class Solution {
    public int solution(int[] nums) {
        int answer = nums.length/2;
        int typeN = Arrays.stream(nums).distinct().toArray().length;
        if (answer > typeN) answer = typeN;
        
        return answer;
    }
}
```
<details>
  <summary>Accuracy Test Results(정확성 테스트 결과)</summary>
  
  ![sol5_accuracy test](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/57a09e7d-0692-4247-b185-706f339f83a6)
</details>
<br>

## My Solution 6
```java
import java.util.Arrays;

class Solution {
    public int solution(int[] nums) {
        int answer = nums.length/2;
        int typeN = Arrays.stream(nums).distinct().toArray().length;
        if (answer > typeN) {
            answer = typeN;
        }
        
        return answer;
    }
}
```
<details>
  <summary>Accuracy Test Results(정확성 테스트 결과)</summary>
  
  ![sol6_accuracy test](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/39ed461a-5817-451f-a689-a6e26a34066f)
</details>
<br>

## My Solution 7
```java
import java.util.Arrays;

class Solution {
    public int solution(int[] nums) {
        int answer = nums.length/2;
        int typeN = Arrays.stream(nums).distinct().toArray().length;
        if (answer > typeN) {answer = typeN; }
        
        return answer;
    }
}
```
<details>
  <summary>Accuracy Test Results(정확성 테스트 결과)</summary>
  
  ![sol7_accuracy test](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/a1ce4e64-bde5-48bf-913d-8fcf731e1764)
</details>
<br>

*여기까지는 그냥 내가 아는 선에서 더 코드를 조금 수정할 때마다 속도가 달라질까? 어떻게 달라질까? 궁금해 서 써 본 코드*

---

*여기부터는 다른 사람들이 쓴 코드*

## My Solution 
```java
import java.util.Arrays;
import java.util.stream.Collectors;

class Solution {
    public int solution(int[] nums) {
        return Arrays.stream(nums)
                .boxed()
                .collect(Collectors.collectingAndThen(Collectors.toSet(),
                        phonekemons -> Integer.min(phonekemons.size(), nums.length / 2)));
    }
}
```
<details>
  <summary>Accuracy Test Results(정확성 테스트 결과)</summary>
  
  ![sol8_accuracy test](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/9001abe4-9599-4a85-8939-2d87ba6a8d9a)
</details>

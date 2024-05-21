<img src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/8605da06-268c-4eb3-9d78-396a1f659226" alt="Pokemonster" width="100px" align="left">

Beginner | Java

# 해시 | [Pokemon](https://school.programmers.co.kr/learn/courses/30/lessons/1845)


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
## ✔ Solution with HashSet
```java
import java.util.HashSet;

class Solution {
    public int solution(int[] nums) {
        int answer = nums.length/2;
        HashSet<Integer> hs = new HashSet<>();
        
        for(Integer num : nums) {
            hs.add(num);
        }
        
        answer = Integer.min(answer, hs.size());
        
        return answer;
        
    }
}
```
<details>
  <summary>Accuracy Test Results(정확성 테스트 결과)</summary>
  
  ![image](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/cd36f191-0b6c-4b6c-b773-2a914d88aa40)

</details>
<br>

## ✔ Solution with HashMap
```java
import java.util.HashMap;

class Solution {
    public int solution(int[] nums) {
        int answer = nums.length/2;
        HashMap<Integer, Integer> h1 = new HashMap<Integer, Integer>();
        
        for(Integer num : nums) {
            h1.put(num, h1.getOrDefault(num, 0) + 1);
        }
        
        answer = Integer.min(answer, h1.size());
        
        return answer;
        
    }
}
```
<details>
  <summary>Accuracy Test Results(정확성 테스트 결과)</summary>
  
  ![채점 결과](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/290f724d-60d6-4e84-a51a-867ee61fd944)
</details>
<br>

## ✔ Solution with Array and ternary operator
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

## ✔ Solution with Array and `.min()`
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

---

*여기부터는 다른 사람들이 쓴 코드*

## Other Solution 
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

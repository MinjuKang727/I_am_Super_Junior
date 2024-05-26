<img src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/11b3df56-3cac-4e4b-8079-f3b3a51452ea" align="left" width="10%" alt="Programmers">

 | Java | Begginer
# 🎱 K번째 변수

## 문제 설명
배열 array의 i번째 숫자부터 j번째 숫자까지 자르고 정렬했을 때, k번째에 있는 수를 구하려 합니다.

예를 들어 array가 [1, 5, 2, 6, 3, 7, 4], i = 2, j = 5, k = 3이라면

1. array의 2번째부터 5번째까지 자르면 [5, 2, 6, 3]입니다.
2. 1에서 나온 배열을 정렬하면 [2, 3, 5, 6]입니다.
3. 2에서 나온 배열의 3번째 숫자는 5입니다.
배열 array, [i, j, k]를 원소로 가진 2차원 배열 commands가 매개변수로 주어질 때, commands의 모든 원소에 대해 앞서 설명한 연산을 적용했을 때 나온 결과를 배열에 담아 return 하도록 solution 함수를 작성해주세요.

### 제한사항
- array의 길이는 1 이상 100 이하입니다.
- array의 각 원소는 1 이상 100 이하입니다.
- commands의 길이는 1 이상 50 이하입니다.
- commands의 각 원소는 길이가 3입니다.

### 입출력 예
| **array**             | **commands**                      | **return** |
|-----------------------|-----------------------------------|------------|
| [1, 5, 2, 6, 3, 7, 4] | [[2, 5, 3], [4, 4, 1], [1, 7, 3]] | [5, 6, 3]  |

### 입출력 예 설명
[1, 5, 2, 6, 3, 7, 4]를 2번째부터 5번째까지 자른 후 정렬합니다. [2, 3, 5, 6]의 세 번째 숫자는 5입니다.  
[1, 5, 2, 6, 3, 7, 4]를 4번째부터 4번째까지 자른 후 정렬합니다. [6]의 첫 번째 숫자는 6입니다.  
[1, 5, 2, 6, 3, 7, 4]를 1번째부터 7번째까지 자릅니다. [1, 2, 3, 4, 5, 6, 7]의 세 번째 숫자는 3입니다.  

---

## Solution with `CopyOfRange()` & `sort()`
```java
import java.util.Arrays;
class Solution {
    public int[] solution(int[] array, int[][] commands) {
        int[] answer = new int[commands.length];
        
        for (int i = 0; i < commands.length; i++) {
            int[] range = commands[i];
            int[] arr = Arrays.copyOfRange(array, range[0] - 1, range[1]);
            
            Arrays.sort(arr);
            
            answer[i] = arr[range[2] - 1];
        }
        
        return answer;
    }
}
```
<details>
  <summary>채점 결과</summary>

  ![image](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/a3f2e580-69fd-4fb3-b241-bd7c4f8f1a6d)
</details>

## 💥 어떤 문제가 있었고, 나는 어떤 시도를 했는지💦  
- 배열의 특성 인덱스 범위를 자르는 방법 찾기
  > 예전에 `copyOfRange()`메서드를 본 적이 있어서 이 메서드를 사용하려고 했는데 매개변수를 어떻게 넣는지 정확히 기억나지 않아서 검색해 봄.

<br>

## 어떻게 해결했는지👍  
- `copyOfRange()`메서드에 2차원 배열인 command에서 배열을 꺼내 복사 범위 설정
  - `Arrays.copyOfRange(array, range[0] - 1, range[1])`
<br>

## 💬 무엇을 새롭게 알았는지  
- 배열을 복사할 수 있는 다른 메서드들도 알게 되었다.
  - `B = A` : 주소값 복사
  - `clone()` : 새로운 메모리에 배열의 값 복사
  - `System.arraycopy(Object o1, int idx1, Object o2, int idx2, int len)` : 배열 `o1`의 `idx1`번 인덱스부터 `len`개의 원소를 배열 `o2`의 `idx2`번 인덱스를 시작 위치로해서 복사
  - `Arrays.copyOf(복사할 배열, int len)` : 복사할 배열을 `0`번 인덱스부터 `len`개의 원소를 복사
  - `Arrays.copyOfRange(복사할 배열, int idx1, int idx2)` : 복사할 배열의 `idx1`~`idx2 - 1`번 인덱스의 원소를 복사
  

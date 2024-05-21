99클럽 2기 | 자바 | 비기너
# 🏃‍♂️ 해시 | 완주하지 못한 선수

## 문제 설명
수많은 마라톤 선수들이 마라톤에 참여하였습니다. 단 한 명의 선수를 제외하고는 모든 선수가 마라톤을 완주하였습니다.

마라톤에 참여한 선수들의 이름이 담긴 배열 participant와 완주한 선수들의 이름이 담긴 배열 completion이 주어질 때, 완주하지 못한 선수의 이름을 return 하도록 solution 함수를 작성해주세요.

## 제한사항
- 마라톤 경기에 참여한 선수의 수는 1명 이상 100,000명 이하입니다.
- completion의 길이는 participant의 길이보다 1 작습니다.
- 참가자의 이름은 1개 이상 20개 이하의 알파벳 소문자로 이루어져 있습니다.
- 참가자 중에는 동명이인이 있을 수 있습니다.
  
## 입출력 예
| **participant**                                   | **completion**                           | **return** |
|---------------------------------------------------|------------------------------------------|------------|
| ["leo", "kiki", "eden"]                           | ["eden", "kiki"]                         | "leo"      |
| ["marina", "josipa", "nikola", "vinko", "filipa"] | ["josipa", "filipa", "marina", "nikola"] | "vinko"    |
| ["mislav", "stanko", "mislav", "ana"]             | ["stanko", "ana", "mislav"]              | "mislav"   |

## 입출력 예 설명

**예제 #1**  
"leo"는 참여자 명단에는 있지만, 완주자 명단에는 없기 때문에 완주하지 못했습니다.

**예제 #2**  
"vinko"는 참여자 명단에는 있지만, 완주자 명단에는 없기 때문에 완주하지 못했습니다.

**예제 #3**  
"mislav"는 참여자 명단에는 두 명이 있지만, 완주자 명단에는 한 명밖에 없기 때문에 한명은 완주하지 못했습니다.

*※ 공지 - 2023년 01월 25일 테스트케이스가 추가되었습니다.*

---

## ✔ Solution with .EntrySet()
```java
import java.util.HashMap;
import java.util.Map.Entry;

class Solution {
    // participant : 참여한 선수 이름 배열
    // completion : 완주한 선수 이름 배열
    // 미완주 선수 1명
    public String solution(String[] participant, String[] completion) {
        
        String answer = "";
        
        HashMap<String, Integer> hm = new HashMap<>();
        int n_participant = participant.length;
        
        for (int i = 0; i < n_participant; i++) {
            String p_runner = participant[i];
            hm.put(p_runner, hm.getOrDefault(p_runner, 0) + 1);
            if (i != n_participant - 1) {
                String c_runner = completion[i];
                hm.put(c_runner, hm.getOrDefault(c_runner, 0) - 1);
            }
            
        }
                
        for (Entry<String, Integer> entry : hm.entrySet()) {
            if(entry.getValue() == 1) return entry.getKey();
        }
        return answer;
    }
}
```

<details>
    <img src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/7d263e65-6251-4c14-9bd1-32c254c44ae7" alt="채점 결과">
    <summary>채점 결과</summary>

</details>

## ✔ Solution with .keySet()
```java
import java.util.HashMap;

class Solution {
    // participant : 참여한 선수 이름 배열
    // completion : 완주한 선수 이름 배열
    // 미완주 선수 1명
    public String solution(String[] participant, String[] completion) {
        
        String answer = "";
        
        HashMap<String, Integer> hm = new HashMap<>();
        int n_completion = completion.length;
        String p_runner, c_runner;
        
        for (int i = 0; i < n_completion; i++) {
            p_runner = participant[i];
            c_runner= completion[i];
                     
            hm.put(p_runner, hm.getOrDefault(p_runner, 0) + 1);
            hm.put(c_runner, hm.getOrDefault(c_runner, 0) - 1);
        }
        p_runner = participant[n_completion];
        hm.put(p_runner, hm.getOrDefault(p_runner, 0) + 1);
                
        for (String runner : hm.keySet()) {
            if(hm.get(runner) == 1) {
                answer = runner;
                break;
            }
        }
        return answer;
    }
}
```
<details>
    <img src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/f52ee06c-5004-4844-a30a-fff1c64dbfd9" alt="채점 결과">
    <summary>채점 결과</summary>

</details>

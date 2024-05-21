# 99 클럽 2기 문제 은행

## 비기너
- [x] [포켓몬](https://school.programmers.co.kr/learn/courses/30/lessons/1845)  
  <details>
    <summary>문제 풀이 인증</summary>
    
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
    <img alt="Programmers_pokemon" src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/3996d3ea-31b6-4a56-bfa0-b1e73db931d6">
  </details>
<br>

- [x] [완주하지 못한 선수](https://school.programmers.co.kr/learn/courses/30/lessons/42576)
  <details>
    <summary>문제 풀이 인증</summary>
    
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

    <img alt="Programmers - incompleted runner" src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/1383712c-2f04-4960-a522-f7c1419b8374">
  </details>
<br>

## 미들러
- [ ] [전화번호 목록](https://school.programmers.co.kr/learn/courses/30/lessons/42577)  
  <details>
    <img alt="" src="" width="50%" align="right">
    <summary>문제 풀이 인증</summary>
    
    ```java
   
    ```
  </details>
  <br>
  

## 챌린저
- [ ] [베스트 앨범](https://school.programmers.co.kr/learn/courses/30/lessons/42579)  
  <details>
    <img alt="" src="" width="50%" align="right">
    <summary>문제 풀이 인증</summary>
    
    ```java
   
    ```
  </details>
  <br>
  
- [ ] 
  <details>
    <img alt="" src="" width="50%" align="right">
    <summary>문제 풀이 인증</summary>
    
    ```java
   
    ```
  </details>

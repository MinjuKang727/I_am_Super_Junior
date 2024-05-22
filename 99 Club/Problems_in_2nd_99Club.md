# 99 클럽 2기 문제 은행

## 비기너
- [x] [포켓몬](https://school.programmers.co.kr/learn/courses/30/lessons/1845)  
  <details>
    <summary>문제 풀이 인증</summary>

    <br> 더 많은 풀이([링크🔗](https://github.com/MinjuKang727/I_am_Super_Junior/blob/5de57f3953d86fb130ce55beb029934843d47e54/99%20Club/Problem_Solving/%5BBegginer%5DPokemon.md))
    
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

    <br> 더 많은 풀이([링크🔗](https://github.com/MinjuKang727/I_am_Super_Junior/blob/main/99%20Club/Problem_Solving/%5BBegginer%5DAn_incompleted_runner.md))
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

- [x] [같은 숫자는 싫어](https://school.programmers.co.kr/learn/courses/30/lessons/12906)
  <details>
      <summary>문제 풀이 인증</summary>
  
      <br> 더 많은 풀이([링크🔗](https://github.com/MinjuKang727/I_am_Super_Junior/blob/26ea2f28d5e17f1c34de713519e261b29d71c927/99%20Club/Problem_Solving/%5BBegginer%5DI_hate_same_numbers.md))
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
  
      <img alt="풀이 인증 사진" src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/733577e5-fbd2-44ff-bd58-c5c3de07c84f">
    </details>
<br>
      
## 미들러
- [x] [전화번호 목록](https://school.programmers.co.kr/learn/courses/30/lessons/42577)  
  <details>
    <summary>문제 풀이 인증</summary>

    <br>더 많은 풀이([링크🔗](https://github.com/MinjuKang727/I_am_Super_Junior/blob/e5992a2f38d068c79989e74d70ba2f5a6928483a/99%20Club/Problem_Solving/%5BMiddler%5DList_of_Phone_Number.md))
    
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
    
    <img alt="문제 풀이 인증 사진" src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/47fceb33-b9ea-4c6c-aee9-4ecefd697684">
  </details>
  
  <br>
  
- [-] [의상](https://school.programmers.co.kr/learn/courses/30/lessons/42578)

  <details>
    <summary>문제 풀이 인증</summary>

    ```java
    import java.util.*;

    class Solution {
        public int solution(String[][] clothes) {
            int answer = 0;
            
            HashMap<HashSet, Integer> hm = new HashMap<>();
            HashSet<String> allClothes = new HashSet<>();
            
            for (String[] cloth : clothes) {
                allClothes.add(cloth[1]);
                HashSet<String> hs = new HashSet<>();
                hs.add(cloth[1]);
                hm.put(hs, hm.getOrDefault(hs, 0) + 1);
            }
            
            String[] arr = allClothes.toArray(new String[allClothes.size()]);
            while(!hm.containsKey(allClothes)){
                HashMap<HashSet, Integer> tempHm = new HashMap<>();
                
                for (HashSet hs : hm.keySet()) {
                    for (String type : arr) {
                       if (!hs.contains(type)){
                            HashSet<String> nextHs = new HashSet<>();
                            nextHs.add(type);
                            int value = hm.get(hs) * hm.get(nextHs);
                            nextHs.addAll(hs);
                            tempHm.put(nextHs, value);
                        } 
                    }
                }
                for (HashSet hs : tempHm.keySet()) {
                    hm.put(hs, tempHm.get(hs));
                }
            }
            
            while(!hm.containsKey(allClothes)){
                HashMap<HashSet, Integer> tempHm = new HashMap<>();
                
                for (HashSet hs : hm.keySet()) {
                    Iterator<String> it = allClothes.iterator();
                    while(it.hasNext()) {
                        String type = it.next();
                        if (!hs.contains(type)){
                            HashSet<String> nextHs = new HashSet<>();
                            nextHs.add(type);
                            int value = hm.get(hs) * hm.get(nextHs);
                            nextHs.addAll(hs);
                            tempHm.put(nextHs, value);
                        }
                        
                    }
                }
                for (HashSet hs : tempHm.keySet()) {
                    hm.put(hs, tempHm.get(hs));
                }
            }
            
            for (int n : hm.values()) {
                answer += n;
            }
            return answer;
        }
    }
    ```

    <img alt="문제 풀이 인증 사진" src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/0d3683b3-7bb6-4d6d-8a97-572358bd1918">
  
  <details>
    
  <br>
  
- [x] [기능개발](https://school.programmers.co.kr/learn/courses/30/lessons/42586)  
  <details>
    <summary>문제 풀이 인증</summary>

    <br>더 많은 풀이([링크🔗](https://github.com/MinjuKang727/I_am_Super_Junior/blob/main/99%20Club/Problem_Solving/%5BMiddler%5DFunctional_development.md))
    
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

    <img alt="문제 풀이 인증 사진" src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/590ea9ce-09b5-49e0-bed2-c6ddbcc11899">
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

- [ ] [비슷한 단어](https://www.acmicpc.net/problem/2179)  
  <details>
    <summary>문제 풀이 인증</summary>
    
    ```java
   
    ```
    
    <img alt="" src="">
  </details>
  <br>
  
- [x] [다리를 지나는 트럭](https://school.programmers.co.kr/learn/courses/30/lessons/42583)  
  <details>
    
    <summary>문제 풀이 인증</summary>
    
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

    <img alt="문제 풀이 인증 사진" src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/3abd3cc1-db95-48aa-b727-b7035b189242">
  </details>
  <br>
  
- [ ] 
  <details>
    
    <summary>문제 풀이 인증</summary>
    
    ```java
   
    ```
    <img alt="문제 풀이 인증 사진" src="">
  </details>

# [Java] error: non-static variable this cannot be referenced from a static context

<br>

## ⁉ What kind of problems happened? (어떤 문제가 있었는지)

### My code
```java
public class MyClass {
class A {}
class B extends A {}

public static void main(String[] args) {

    A a = new A();
    B b = new B();

    System.out.println("a instanceof A : " + Boolean.toString(a instanceof A));
    System.out.println("b instanceof A : " + Boolean.toString(b instanceof A));
    System.out.println("a instanceof B : " + Boolean.toString(a instanceof B));
    System.out.println("b instanceof B : " + Boolean.toString(b instanceof B));

}
    
}
```
##### Output
```java
MyClass.java:7: error: non-static variable this cannot be referenced from a static context
    A a = new A();
          ^
MyClass.java:8: error: non-static variable this cannot be referenced from a static context
    B b = new B();
          ^
2 errors
```

### ☠ error: non-static variable this cannot be referenced from a static context
<br>

## Things I've tried. (내가 시도해본 것들)💦

- 구글에 에러 `Ctrl + C(복사)`, `Ctrl + V(붙여넣기)` 검색  

  #### 참고 자료
  [[자바(JAVA) 개념] 클래스(class) 선언방법 / 필드 /  생성자](https://devuna.tistory.com/4)  
  [Non-static variable cannot be referenced from a static context](https://stackoverflow.com/questions/2559527/non-static-variable-cannot-be-referenced-from-a-static-context)  
  [[Java] static 변수, static 메서드 그리고 static 클래스](https://velog.io/@mooh2jj/Java-static-%EB%B3%80%EC%88%98-static-%EB%A9%94%EC%84%9C%EB%93%9C-%EA%B7%B8%EB%A6%AC%EA%B3%A0-static-%ED%81%B4%EB%9E%98%EC%8A%A4)

  > 바로 무슨 내용인지 어떻게 에러를 개선해야할 지 모르겠어서 일단 PASS~
  
<br>

## ✔ How did I solve it? (어떻게 해결했는지)
2. 에러를 잘 읽어보니 static이 아닌 변수를 static context 안에서 사용할 수 없다는 말인 것 같아서 그냥 class 선언한 것 앞에 static을 붙여주었는데 실행됨.
   
```java
public class MyClass {
  static class A {}
  static class B extends A {}
  
  public static void main(String[] args) {
  
      A a = new A();
      B b = new B();
  
      System.out.println("a instanceof A : " + Boolean.toString(a instanceof A));
      System.out.println("b instanceof A : " + Boolean.toString(b instanceof A));
      System.out.println("a instanceof B : " + Boolean.toString(a instanceof B)); // true
      System.out.println("b instanceof B : " + Boolean.toString(b instanceof B)); // true
  
  }
}
```

#### Output
```
a instanceof A : true
b instanceof A : true
a instanceof B : false
b instanceof B : true
```
<br>

## 🔆 What did you learn? (무엇을 새롭게 알았는지)




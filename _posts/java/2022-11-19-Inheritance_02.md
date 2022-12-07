---
title : "JAVA - final 클래스, final 메소드, protected 접근 제한자"
layout: single
excerpt: "[JAVA] 상속 (Inheritance) 이론 정리 - 2"
toc: true
toc_sticky: true
date: 2022-11-19
categories: [Java]
tag: [final, protected]
author_profile: false
header:
  overlay_image: assets/images/header_post_1.jpg
  overlay_filter: 0.5 
  teaser: assets/images/java.png
published: true
---

`이것이 자바다` 의 Chapter07 을 참고하여 정리한 포스트입니다.
{: .notice--warning}

# Chapter 07. 상속 - 2

## 5. final 클래스와 final 메소드   

final 키워드는 클래스, 필드, 메소드 선언 시에 사용 가능하며, 해당 선언이 최종 상태이고, 결코 수정될 수 없음을 뜻한다.  

**final 키워드 선언 시 해석**  
  - 필드 선언 시에는 final 이 지정되면 초기값 설정 후, 더 이상 값을 변경할 수 없다.  
  - 클래스와 메소드 선언 시에 final 키워드가 지정되면 상속과 관련이 있다. 

### 5.1 상속할 수 없는 final 클래스   
클래스를 선언 : final 키워드를 class 앞에 붙이게 되면 이 클래스는 최종적인 클래스이므로 상속할 수 없는 클래스가 된다. 
final 클래스는 부모 클래스가 될 수 없어 자식 클래스를 만들 수 없다.  
```java
public final class 클래스 {...}
```  

> **ex)** final 클래스 : 자바 표준 API 에서 제공하는 String 클래스
  ```java
  public final class String {...}
  ```  
String 클래스는 자식 클래스를 만들 수 없다.
  ```java
  public class NewString extends String{...}  //extends String 불가 
  ```

### 5.2 오버라이딩할 수 없는 final 메소드   
final 키워드를 붙이고 메소드를 선언하면 최종적인 메소드가 되기 때문에 오버라이딩(Overriding) 할 수 없는 메소드가 된다.   
```java
public final 리턴타입 메소드( [매개변수, ...] ) {...}
```
> **ex)** 부모 클래스를 상속해서 자식 클래스를 선언할 때,  
위의 양식으로 부모 클래스(Example.java) 에 선언된 final 메소드( check() )는 자식 클래스(Test.java)에서 재정의가 불가능하다.  

```java
public class Test extends Example {
  //check() 메소드 오버라이딩 불가
  @Override
  public void check() {
    ...
  }
}
```

## 6. protected 접근 제한자  
protected 는 public 과 default 접근 제한의 중간 쯤에 해당한다.  

| 접근 제한 | 적용할 내용 | 접근할 수 없는 클래스 |
|----------|-------------|---------------------|
| public | 클래스, 필드, 생성자, 메소드 | 없음 |
| protected | 필드, 생성자, 메소드 | 자식 클래스가 아닌 다른 패키지에 소속된 클래스 |
| default | 클래스, 필드, 생성자, 메소드 | 다른 패키지에 소속된 클래스 |
| private | 필드, 생성자, 메소드 | 모든 외부 클래스 |

같은 패키지에서는 default 와 같이 접근 제한이 없고 다른 패키지에서는 자식클래스만 접근 허용한다.  
<center><img src="/images/2022-11-18-java_Inheritance/protected.png"></center>  

🌞 정보 : 공부 기록용 블로그입니다. 오타나 내용 오류가 있을 경우 알려주시면 감사하겠습니다.
{: .notice}

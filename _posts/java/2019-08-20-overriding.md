---
layout: post
title:  "[Java] 오버라이딩(Overriding)"
date:   2019-08-20 22:01:18
author: Choi HyeSun
categories: java
tags:
  - Java
  - 오버라이딩
  - overriding
  - super()
  - super
  - this()
  - this vs super
  - 오버로딩
  - overloading
---

## 오버라이딩(overriding) - 정의

- 부모클래스로부터 상속받은 메서드의 내용을 변경하는 것

  - overwrite : ~위에 덮어씀

<br>
<br>

## 자식클래스에서 부모클래스로부터 상속받은 메서드를 오버라이딩하는 조건

- 자식클래스에서 오버라이딩하는 메서드는 부모클래스의 메서드와 ( )이 같아야 함

  - 이름 / 매개변수 / 반환타입

  - 즉 선언부가 서로 일치해야 함

- 단, 접근제어자(Access Modifier)와 예외(Exception)은 제한된 조건 하에 다르게 변경할 수 있음

  - 접근 제어자는 조상 클래스의 메서드보다 좁은 범위로 변경할 수 없음 > 넓은 범위나 같은 범위로 사용, 대체로 같은 범위로 사용

  - 조상 클래스의 메서드보다 많은 수의 예외를 선언할 수 없음 > 예외 처리를 분기한 개수가 아니라 범위를 의미<br>IOException + SQLException \< Exception
  
  - 인스턴스 메서드를 static 메서드로 또는 그 반대로 변경할 수 없음
  
<br>
<br>

## 오버로딩 vs 오버라이딩

- 오버로딩(overloading) : 기존에 없는 새로운 메소드를 정의

- 오버라이딩(overriding) : 상속받은 메서드의 내용을 변경

<br>
<br>

## super

- 자식 클래스에서 부모 클래스로부터 상속받은 멤버를 참조하는데 사용되는 참조 변수

- 모든 인스턴스메서드에는 자신이 속한 인스턴스의 주소가 지역변수로 저장

  - this / super

- static 메서드
 
  - this / super 모두 사용 불가

- 사용시점

  - 조작을 할 때 부모클래스에 반영이 되어야 한다면!

<br>
<br>

## this vs super

- this : 멤버변수와 지역변수가 이름이 같을 때 구분 [this - 인스턴스변수]

- super : 상속받은 멤버와 클래스에 정의된 멤버가 이름이 같을 때 구분 [super - 상속값]

  - 즉, 오버라이딩 했을 때 !

  - super.변수 = 상속받은 부모클래스의 변수

  - super.메소드() =  상속받은 부모클래스의 메소드

  - this.변수 = (또는 그냥) 변수 = 자식클래스(본인)의 변수

  - this.메소드() = (또는 그냥) 메소드() = 자식클래스(본인)의 메소드
  
<br>
<br>

## super() - 부모 클래스의 생성자
 
- this() vs super()

  - this() : 같은 클래스의 다른 생성자 호출

  - super() : 부모 클래스의 생성자 호출

- 자식 클래스 생성자에는 부모 클래스의 생성자가 들어가야 함

  - 자식 클래스의 인스턴스 생성
  <br>→ 자식 클래스 멤버(변수+메소드) + 부모 클래스 멤버(변수+메소드) > 하나의 인스턴스
  <br>→ 자식 클래스의 인스턴스가 부모 클래스의 변수에 접근을 해야 함
  <br>→ 초기화 작업 필요
  <br>→ 부모 클래스의 생성자 호출
  <br>→ 자식 클래스의 생성자가 부모 클래스의 멤버를 사용할 수 도 있으므로, 자식 클래스 생성자 첫 줄에 선언

  - Object 클래스를 제외한 모든 클래스의 생성자 첫줄에 생성자.this() 또는 super()를 호출해야 함
  <br>호출 부분이 없다면, 컴파일러가 super();를 생성자 첫 줄에 삽입함
  <br>(유의) 컴파일러는 super();를 생성하는데, 부모클래스에 매개변수가 없는 생성자가 없을 경우 컴파일에러가 발생
- 인스턴스 생성시 고려할 부분

  - 클래스 : 어떤 클래스의 인스턴스를 생성할것인가?
  
  - 생성자 : 선택한 클래스의 어떤 생성자를 이용해서 인스턴스를 생성할것인가?
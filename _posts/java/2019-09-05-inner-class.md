---
layout: post
title:  "[Java] 내부 클래스(inner class)"
date:   2019-09-05 18:11:12
author: Choi HyeSun
categories: java
tags:
  - Java
  - 이너클래스
  - 내부클래스
  - inner class
  - 익명클래스
  - anonymous class
---

## 내부 클래스(inner class) - 정의

- 클래스 내에 선언된 클래스

- 주로 AWT나 Swing같은 GUI어플리케이션의 이벤트처리 외에는 잘 사용되지 않음

- 두 클래스가 서로 긴밀한 관계

- 내부 클래스가 외부 클래스를 제외하고 다른 클래스에서 (잘) 사용되지 않아야 함

<br> 
<br> 

## 내부 클래스(inner class) - 장점

- 내부 클래스에서 외부 클래스의 멤버들을 쉽게 접근 가능

- 코드의 복잡성을 줄일 수 있음(캡슐화)

<br> 
<br> 

## 내부 클래스(inner class) - 종류 및 선언

- 변수의 선언위치에 따른 종류와 동일

|내부 클래스|특징|
|---|---|
|인스턴스 클래스<br>(instance class)|외부 클래스의 멤버변수 선언 위치에 선언<br>외부 클래스의 인스턴스 멤버처럼 사용<br>외부 클래스의 인스턴스 멤버와 관련된 작업에 사용될 목적|
|스테틱 클래스<br>(static class)|외부 클래스의 멤버변수 선언 위치에 선언<br>외부 클래스의 static 멤버처럼 사용<br>외부 클래스의 static 멤버, 특히 static 메서드에서 사용될 목적<br>내부에 static 변수가 있을 경우, static 클래스로 정의(단 final static은 상수이므로 관계 없음)|
|지역 클래스<br>(local class)|외부 클래스의 메서드나 초기화 블럭 안에 선언<br>선언된 영역 내부에서만 사용<br>같은 이름|
|익명 클래스<br>(anonymous class)|클래스의 선언과 객체의 생성을 동시에 하는 이름없는 일회용 클래스|

<br>
<br>

## 내부 클래스(inner class)의 제어자 

- 내부 클래스가 외부 클래스의 멤버와 같이 간주

  - 인스턴스멤버와 static 멤버간의 규칙이 내부 클래스에도 똑같이 적용

  - private, protected와 접근제어자 사용 가능

- 클래스이기 때문에 abstract / final 사용 가능

<br>
<br>

## 내부 클래스(inner class) - 접근성

- 외부 클래스의 멤버가 private 접근제어자일 경우에도 사용 가능

- 내부 지역 클래스의 경우 외부 메서드에 정의된 지역 변수도 사용할 수 있음

  - 단, final이 붙은 지역 변수만 접근 가능
  <br>메서드가 수행을 마쳐서 지역변수가 소멸된 시점에도, 지역 클래스의 인스턴스가 소멸된 지역변수를 참조하려는 경우가 발생할 수 있기 때문

  - 접근하려는 지역 변수 앞에 final을 생략할 수 있음(컴파일러가 자동으로 붙여줌. JDK1.8~)
  <br>(유의) 외부 지역변수 앞에 final을 붙여주는 것이기 때문에, 만약 그 지역변수 값을 변경하는 부분이 있다면 컴파일러 에러 발생

<br>
<br>

## 내부 클래스(inner class) - 컴파일시

- 파일명 : 외부클래스명$내부클래스명.class로 생성됨

- 지역 내부 클래스 : 외부클래스명$n내부클래스명.class

  - 다른 메서드에 같은 이름의 지역 내부 클래스가 존재할 수 있기 때문에 번호가 붙음
  
<br>
<br>

## 내부 클래스와 외부 클래스에 선언된 변수의 이름이 같을 때

- 외부클래스명.this ←를 붙여서 구분

  - 예-내부클래스의 지역변수) sunny;

  - 예-내부클래스의 클래스변수) this.sunny;

  - 예-외부메서드의 클래스변수) Weather.this.sunny;
  
<br>
<br>

## 익명클래스(anonymous class) - 특징

- 다른 내부 클래스들과는 달리 이름이 없음

  - 생성자도 가질 수 없음

  - 단 하나의 클래스를 상속받거나 인터페이스를 구현할 수 있음
  <br>→ 2개 이상일 경우 이름으로 정의하기 때문

- 클래스의 선언과 객체 생성을 동시에 진행

  - 단 한번만 사용될 수 있음

  - 오직 하나의 객체만을 생성할 수 있는 일회용 클래스

<br>
<br>

## 익명클래스(anonymous class) - 선언

  - new 상속부모클래스이름() { //멤버 선언 }

  - new 구현인터페이스이름() { //멤버 선언 }

<br>
<br>

## 익명클래스(anonymous class) - 컴파일

  - 외부클래스명$n.class 형식으로 결정
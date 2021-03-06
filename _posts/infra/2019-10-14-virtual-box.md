---
layout: post
title:  "[Virtual Box] 설치하기"
date:   2019-10-14 13:12:31
author: Choi HyeSun
categories: infra
tags:
  - VirtualBox
  - VM
  - VirtualBox설치
  - VirtualBox6.0.12
---

## 1. Virtual Box 다운로드
다운로드 [LINK](https://www.virtualbox.org/wiki/Downloads)
  - 원하는 운영체제 선택
  ![image](/img/2019-10-14/Virtual-Box-001-Downloads.png)

<br>
<br>

## 2. Download한 설치파일 실행
VirtualBox-6.0.12-133076-Win.exe(버전명은 다운로드한 버전) 실행 후 설치
  - Next>
  ![image](/img/2019-10-14/Virtual-Box-002-setup1.png)
  
  - 경로설정(Browse) → Next>
  ![image](/img/2019-10-14/Virtual-Box-003-setup2.png)
  
  - 다운로드할 부분 체크 → Next>
  ![image](/img/2019-10-14/Virtual-Box-004-setup3.png)

  - Yes (대충 네트워크 설정 바뀐다는 경고창)
  ![image](/img/2019-10-14/Virtual-Box-005-setup4.png)

  - Install (대충 설정 바꿀거면 다시 바꾸라는 경고창)
  ![image](/img/2019-10-14/Virtual-Box-006-setup5.png)
  
  - 설치중 (기다리기)
  ![image](/img/2019-10-14/Virtual-Box-007-setup6.png)
  
  - Finish (완료)
  ![image](/img/2019-10-14/Virtual-Box-008-setup7.png)

<br>
<br>

## 3. Virtual Box 실행
  - 실행화면
  ![image](/img/2019-10-14/Virtual-Box-009-start1.png)
  
  - 버전확인 (도움말 > VirtualBox 정보)
  ![image](/img/2019-10-14/Virtual-Box-010-start2.png)
  ![image](/img/2019-10-14/Virtual-Box-011-start3.png)

<br>
<br>

## 4. 기본 환경 설정
  - 환경설정 메뉴 들어가기 (파일 > 환경설정)
  ![image](/img/2019-10-14/Virtual-Box-012-settings1.png)
  ![image](/img/2019-10-14/Virtual-Box-013-settings2.png)

  - 기본 머신 폴더(서버 생성하면 저장되는 폴더) 변경하기 - 일반탭
  ![image](/img/2019-10-14/Virtual-Box-014-change.png)
  
<br>
<br> 

## 5. 호스트키 조합 변경
호스트키 : VirtualBox에 마우스를 클릭하게 되면 서버 안으로 들어가서 원래 컴퓨터로 다시 마우스를 내보내려면 호스트키를 입력해야함
  - 기본값 : Right Control
  - 변경 희망값 : Ctrl + Alt

<br>
호스트키 변경하기
  - 파일 → 환경설정 → 입력 → 가상머신(탭)
  ![image](/img/2019-10-14/Virtual-Box-015-HostKey1.png)
  
  - 호스트 키 조합의 단축키 클릭
  ![image](/img/2019-10-14/Virtual-Box-016-HostKey2.png)
  
  - Ctrl + Alt 키를 누르면 자동으로 입력됨 → 확인
  ![image](/img/2019-10-14/Virtual-Box-017-HostKey3.png)
  
<br>
<br>

## 끝
이제 Virtual Box를 쓸 수 있고, Virtual Box에 Server를 설치해서 공부할 예정

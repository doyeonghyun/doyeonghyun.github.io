---
title: "[유니티] Button UI의 On Click()의 No Function에서 Monoscript만 보이는 오류"
tags: 
- 오류 기록
- 유니티
---

## **에러:Button UI의 On Click()의 No Function에서 Monoscript만 보일 때**

![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/28aa28c0-adfc-4d41-932b-d257e13f1e9b)

버튼(Button) UI 중 On Click()에서 사용할 스크립트를 넣은 후 함수를 확인하려고 No Function을 클릭하자 MonoScript만 나오는 오류가 나타났다. 

***

### 해결방법

C# 스크립트가 아닌 자신이 사용할 스크립트와 연결된 Object를 선택해야 된다.

My Ball이라는 스크립트를 넣으면 안되고 My Ball과 연결된 Sphere라는 개체를 넣어야 한다.

![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/68d89c8b-67d9-4f87-bf47-e85203eea355)

그러면 이제 자신이 넣으려는 함수가 나오는 것을 볼 수 있다.

***

### 기타

위 방법으로 했는데도 함수가 나오지 않는다면 스크립트 안에서 해당 함수를 public으로 적었는지 확인해본다.

![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/611095a8-7c38-411f-a27f-642601f30d7d)

![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/f6e550bb-74f4-4a19-8cf8-c8566ee8e96f)

---
title: "[유니티] It looks like you want to tile a sprite with no border"
tags:
 - 오류 기록
 - 유니티
---

## **에러:It looks like you want to tile a sprite with no border.**

![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/e3b39850-7321-4239-9d90-7bafeac4add3)

>It looks like you want to tile a sprite with no border.
>It would be more efficient to modify the Sprite properties,
>clear the Packing tag and set the Wrap mode to Repeat.

이미지 타입을 Tiled로 바꿀 때 나타나는 오류다.

***

### 해결방법

1. source image로 사용한 파일의 Wrap Mode를 Repeat로 바꾼다. 이때 새로운 오류가 나올 수 있는데 해결 방법은 아래에 작성했다. 
  
   ![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/1755c84e-6198-4fd9-b21b-c9a79a1809c1)

***

### 기타 오류


1. Only textures with width/height being multiple of 4 can be compressed to DXT5 BC3 format는 넓이와 높이가 4의 배수인 텍스쳐만 DXT5 BC3 포맷으로 압축이 가능하다는 내용이다. 따라서 사진의 크기를 확인해야 된다.

   ![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/1746bbab-09b1-4273-8332-b5f6121e7b79)

   왼쪽 사진이 원본 사진 크기인데 4의 배수가 아닌 것을 확인할 수 있다. 따라서 오른쪽처럼 4의 배수로 바꾼다면 이미지가 나온다.

   ![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/aff55bc1-8417-40b9-af7f-acfbfc82e70e)

   다른 방법으로는 이미지 설정을 다음과 같이 변경해도 오류는 없다.

   ![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/f35df55e-6cf0-49cd-a05e-d802962764a5)

   ![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/f74881c9-e911-4aec-b824-de0d6fa4e813)
<br/><br/>

2. This Image doesn't have a border.

  ![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/ea307651-f381-4256-8b55-ecb4f6d437f8)
   
   Window > Package manager로 들어간 후 2021.3.32f1 기준으로 Packages: Unity Registry에서 2D sprite를 설치한다.

   ![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/ce9a88c7-6446-4411-ac4d-1fd7f9f92a98)

   이후에 이미지 Inspector에 들어가면 텍스쳐 타입이 Sprite인 경우에 Sprite Editor를 확인할 수 있다.

   ![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/15546b5b-0bc1-4a1a-a28c-5ef525a4f9ca)

   Sprite Editor 창으로 통해 Border값을 LRTB 중 하나라도 수정하고 save하면 해당 오류가 나오지 않는 것을 확인할 수 있다.

   ![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/59182b7f-85fd-4477-bb98-dd2a46d7f401)


***

#### 참조
[https://fiftiesstudy.tistory.com/258](https://fiftiesstudy.tistory.com/258)

[https://sunpil.tistory.com/482](https://sunpil.tistory.com/482)

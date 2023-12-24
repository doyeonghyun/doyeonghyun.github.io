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

1. source image로 사용한 파일의 Wrap Mode를 Repeat로 바꾼다.
![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/1755c84e-6198-4fd9-b21b-c9a79a1809c1)

>Only textures with width/height being multiple of 4 can be compressed to DXT5|BC3 format
>


---
title: "[유니티] Shader channels Normal and Tangent are most often used with lighting"
tags: 
- 오류 기록
- 알고리즘
---

## **에러:Shader channels Normal and Tangent are most often used with lighting**

![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/57bb488f-8cbc-4f56-9760-8d17fb9d5a74)


> Shader channels Normal and Tangent are most often used with lighting,
> which an Overlay an Overlay canvas does not support.
> Its likely these channels are not needed.

Canvas에서 발견할 수 있는 오류다.

***

### 해결방법

해당 오류를 번역하면 다음과 같다.

> Shader 채널 Normal 및 Tangent는 오버레이 캔버스가 지원하지 않는 조명과 함께 가장 자주 사용됩니다. 이러한 채널은 필요하지 않을 가능성이 높습니다.

경고 메시지에 가까운 내용이다. 다음 내용은 Additional Shader Channel에서 확인할 수 있다.

![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/9485d002-c6c2-4d6c-9151-482bb123606e)

체크한 내용을 해제하면 메시지가 사라지는 것을 볼 수 있다.

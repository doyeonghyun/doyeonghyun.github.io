---
title: "[C++] cin, cout, printf, scanf 함수에 대해서"
tags: 
 - C++
---

![](https://velog.velcdn.com/images/doyeong0526/post/e0618787-9b8e-4ce9-ba68-199b787a2467/image.PNG)


이전에 풀어보았던 BOJ10950 문제. 연산을 하는 데 cin, cout 함수를 사용했더니 메모리 2020KB, 시간 4ms이 걸린다. 

```
ios_base::sync_with_stdio(false);
cin.tie(NULL);
```
버퍼 동기화를 끊고 tie를 풀어주는 함수라고 한다. iostream이 cstdio랑 동일한 버퍼시스템을 사용해서 scanf, printf를 호출한다고 들었다. 이것을 사용하지 않아서 걸렸나보다~ 하고 메인함수에 추가적으로 작성했더니 똑같았다.(2번째 제출)<br/><br/>

코드를 엉성하게 짰나 고민도 하고 실제로 그게 맞을지도 모른다. 그러나 아직 잘 모르겠다... 그래서 한번 이것저것 찾아보다가 scanf, printf함수를 사용하면 메모리 사용과 속도 면에서 좋다고 하길래 제출한 결과가 3번째 제출이다. 메모리 1112KB, 시간 0ms. <br/><br/>

실제 코드를 비교하자면 다음과 같다.

***

### cin, cout함수

```
#include <iostream>
using namespace std;
int T, A, B;

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
	cin >> T;
	for (int i = 0; i < T; i++) {
		cin >> A >> B;
		cout << A + B << endl;
	}
	return 0;
}
```

### scanf, printf 함수

```
#include <cstdio>
int T, A, B;

int main() {
	scanf("%d \n", &T);
	for (int i = 0; i < T; i++) {
		scanf("%d %d", &A, &B);
		printf("%d\n", A + B);
	}
	return 0;
}
```

***

처음에 scanf, printf 함수를 사용하는 게 코테에 더 유리하지 않은가 싶었는데 사람들은 cin, cout 함수를 더 이용하고 있다. 이유를 들어보면 **안정성, 확정성**에 있다고 한다. 속도는 데이터 형식이 지정되지 않는 점에서 느리다. <br/><br/>

그러니 결론적으로 **안정성과 확정성을 보장받기 위해선 cin, cout 함수 사용을 권장**하는 느낌이다. 

앞서 작성한 ios_base::sync_with_stdio(false)와 cin.tie(NULL)을 같이 작성하면 전보다 속도는 빨라진다는데 내가 제출한 결과에서는 똑같아서 아직까진 체감이 되지 않았다. 그러나 역시 상황에 따라서는 scanf, printf 함수 사용도 고려하는게 좋을 것 같다!

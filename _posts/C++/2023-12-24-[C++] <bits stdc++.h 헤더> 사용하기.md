---
title: "[C++] <bits/stdc++.h 헤더> 사용하기"
tags: 
 - C++
---

저번에 비쥬얼 스튜디오를 다시 설치하는 과정에서 bits/stdc++.h 헤더가 사라졌다. 이 사실도 모르고 이때까지 #include <iostream>을 쓰고 있었다. 이 헤더의 존재를 자주 까먹어서 위 글을 작성한다.

***

## bits/stdc++.h 헤더 정보

1. #include <bits/stdc++.h>
2. 자주 사용하는 라이브러리들을 컴파일하여 일일이 추가하는 번거로움을 없애서 **코테에 쓰기 유용한 헤더 파일** 이다.
3. 불필요한 라이브러리도 컴파일이 되면서 시간과 공간이 낭비된다는 단점이 있기 때문에 **개발환경에서는 사용하지 않는 것이 좋다.**

<details>
<summary><bits/stdc++.h> 내부</summary>

<div markdown="1">
***

```
#pragma once
#include <cctype>
#include <cerrno>
#include <cfloat>
#include <ciso646>
#include <climits>
#include <clocale>
#include <cmath>
#include <csetjmp>
#include <csignal>
#include <cstdarg>
#include <cstddef>
#include <cstdio>
#include <cstdlib>
#include <cstring>
#include <ctime>

#include <ccomplex>
#include <cfenv>
#include <cinttypes>
#include <cstdalign>
#include <cstdbool>
#include <cstdint>
#include <ctgmath>
#include <cwchar>
#include <cwctype>

// C++
#include <algorithm>
#include <bitset>
#include <complex>
#include <deque>
#include <exception>
#include <fstream>
#include <functional>
#include <iomanip>
#include <ios>
#include <iosfwd>
#include <iostream>
#include <istream>
#include <iterator>
#include <limits>
#include <list>
#include <locale>
#include <map>
#include <memory>
#include <new>
#include <numeric>
#include <ostream>
#include <queue>
#include <set>
#include <sstream>
#include <stack>
#include <stdexcept>
#include <streambuf>
#include <string>
#include <typeinfo>
#include <utility>
#include <valarray>
#include <vector>
#include <array>
#include <atomic>
#include <chrono>
#include <condition_variable>
#include <forward_list>
#include <future>
#include <initializer_list>
#include <mutex>
#include <random>
#include <ratio>
#include <regex>
#include <scoped_allocator>
#include <system_error>
#include <thread>
#include <tuple>
#include <typeindex>
#include <type_traits>
#include <unordered_map>
#include <unordered_set>
```
</div>
</details>

***

### 설치 과정

파일을 직접 다운받아서 파일에 넣어줘야 한다. 서치하면 파일이 나오긴 하지만 본인은 [코테 레포지토리](https://github.com/doyeonghyun/Coding-test/tree/main/%ED%97%A4%EB%8D%94%ED%8C%8C%EC%9D%BC)에 헤더 파일을 따로 추가해뒀다.

> 경로: C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.38.33130\include
>
> 설치 환경에 따라 경로의 차이가 있을 수 있다.

include 파일 안에 bits 파일 생성 후 stdc++.h 헤더 넣기
![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/cca5b82b-53e9-4971-b7d3-73861393d564)
![image](https://github.com/doyeonghyun/doyeonghyun.github.io/assets/68155575/c8a9d2c0-4a25-4565-92c0-66b15d1e3c30)


Count by X (2022.03.23)
===
**Problem**   

> - X의 배수를 n만큼 출력
> ![Problem Image](https://user-images.githubusercontent.com/80976609/159629456-99fc5fbc-624e-497a-aadc-293ddbe26845.png)   
   
   
**Solution :**
- for문을 이용하여 n개를 벡터에 추가
```cpp
#include <vector>
std::vector<int> countBy(int x,int n){
    std::vector<int> vec;
  
    for(int i = 1; i <= n; i++) {
        vec.push_back(x * i);
    }
  
    return vec;
}
```   
   
- 람다식을 활용하여 간략화

```cpp
#include <vector>
std::vector<int> countBy(int x,int n){
    std::vector<int> vec(n);
    std::generate(vec.begin(), vec.end(), [i = 0, &x] () mutable {return i += x;});
    return vec;
}
```


**Link :**
- [std::vector<T> Methods](https://www.cplusplus.com/reference/vector/vector/)
- [lambda expressions](https://docs.microsoft.com/ko-kr/cpp/cpp/lambda-expressions-in-cpp?view=msvc-170)
- [fill vector by std::generate](https://en.cppreference.com/w/cpp/algorithm/generate)
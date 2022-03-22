String ends with? (2022.03.22)
===
**Problem**   

> - 문자열의 끝부분이 다음 문자열과 같은지를 비교하는 문제
> ![Problem Image](https://user-images.githubusercontent.com/80976609/159496344-10b934dd-7611-49dd-a7d4-7ba6e53b7b5f.png)   
   
   
**Solution :**
- 두 문자열을 끝 부터 비교하는 방법
```cpp
#include <string>

using namespace std;
 
bool solution(string const &str, string const &ending) {
    // 변수 선언 *_index => 문자열의 끝 번호, compare => 비교할 문자 수
    int str_index = str.size() - 1; 
    int ending_index = ending.size() - 1;
    int compare = (str_index < ending_index) ? str_index : ending_index;
   
    for(int i = 0; i <= compare; i++) {
       // 다르면 false return
       if(str[str_index - i] != ending[ending_index - i])
            return false;
    }
   
    return true;
}
```   
   
- string의 compare method 활용

```cpp
#include <string>

bool solution(std::string const &str, std::string const &ending) {
    return str.size() >= ending.size() && str.compare(str.size() - ending.size(), ending.size(), ending) == 0;
}
```
**Link :**
- [std::string::compare()](https://www.geeksforgeeks.org/stdstringcompare-in-c/?ref=lbp)
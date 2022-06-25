# Code Examples

```cpp
// Some code
#include <iostream>
using namespace std;

int main(){
    char *alph = (char *)malloc(26);
    for(int i=0; i < 26;i++){
            alph[i] = 65 +i;
        }
    cout << alph << endl;
    free(alph);
    return 0;
}
```

This code demonstrates why C is bad. Thank You.

Just to familiarize myself with md tables.

|  | CompSci | Algebra | Discrete Maths | English |
| --- | --- | --- | --- | --- |
| Week 1 | 2h | 3h | 3h | 3h |
| Week 2 | 12h | 10h | 8h | 0 |
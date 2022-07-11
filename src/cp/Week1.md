# Week 1

## Topics Covered
- What is competitive programming
- [Input and output](#input-and-output)
- [Handling numbers](#numbers)
- [Macros and code shortening](#macros)
- [Recursion](#recursion)
    - Subsets
    - Permutations
    - Backtracking
- [Bits](#bits)


### Input and output
For faster input in c++ the code below is used, well explained [here](https://stackoverflow.com/a/31165481)
```cpp
ios::sync_with_stdio(0); cin.tie(0);
```
Also, `\n` works faster than `std::endl`

If amount of data is not given:
```cpp
while(cin >> x){
    //code
}
```

For input and output using files:
```cpp
freopen("input.txt", "r", stdin);
freopen("output.txt", "w", stdout);
```

### Numbers

Most used types are int and long long.

Modular Arithmetic:
```
(a+b) mod m = (a mod m + b mod m) mod m
(a-b) mod m = (a mod m - b mod m) mod m
(a*b) mod m = (a mod m * b mod m) mod m
```
It's used when the answer is too big, even for ll.

### Macros

For code shortening the best macros are:

```cpp
#define ll long long
#define ld long double
#define vt vector
#define vi vector<int>
#define pb push_back
#define FASTIO ios::sync_with_stdio(0); cin.tie(0);
#define nl "\n"
#define sp " "
#define FOR(i, a, b) for (int i=a; i<b; i++)
```
So that code below
```cpp
vector<int> arr;
for (long long i = 0; i < nums.size(); i++){
    arr.push_back(i);
    cout << i << "\n";
}
```
can be turned into
```cpp
vi arr;
FOR(i,0,nums.size()){
    arr.pb(i);
    cout << i << nl;
}
```

### Recursion

Subsets - [link](https://github.com/SamirTheCreator/code/blob/main/c%2B%2B/subsets.cpp)

Permutations - [link](https://github.com/SamirTheCreator/code/blob/main/c%2B%2B/permutations.cpp)

Queen problem - [link](https://github.com/SamirTheCreator/code/blob/main/c%2B%2B/queens.cpp)

### Bits

There are various ways to manipulate bits and many usecases in competitive programming

Bit shifts `<<` and `>>` append 0 to either left or right and shift the bit representation of the number to the same direction. `x << n` means multiplying x by 2<sup>n</sup> and `x >> n` means dividing x by 2<sup>n</sup>. 

Bit masks can be used to represent a number in bits. For example, mask `1 << k` has 1 in kth position and all other bits are set to 0.
```cpp
int x = 4453;
for (int i=31; i >= 0; i--){
    if (x & (1 << k)) cout << 1;
    else cout << 0;
}
```
Other formulas:
- `x | (1 << k)` sets kth bit of x to 1;
- `x & ~(1 << k)` sets kth bit of x to 0;
- `x ^ (1 << k)` inverts kth bit of x;
- `x & (x-1)` sets the last bit to 0;
- `x & -x` sets all the 1s to 0s excluding last bit;
- `x | (x-1)` inverts all bits excluding last bit;
- `x & (x-1)` is 0 when the number is a power of 2;

However, it's hard to work with masks using any other type except `int`. To create a mask for a `long long` `1LL << k` can be used.

g++ compiler also has built in functions to work with bits:
- `__builtin_clz(x)` returns the number of zeros at the beginning
- `__builtin_ctz(x)` returns the number of zeros at the end
- `__builtin_popcount(x)` return the number of ones
- `__builtin_parity(x)` returns 1 if even, 0 if odd

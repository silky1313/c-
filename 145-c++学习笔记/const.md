# const

## 1.常函数

```c++
struct Ds{
    int fa[N];
    Ds(int n){
        for(int i = 1; i <= n; i++){
            fa[i] = i;
        }
    }
    int find(int x) const{//const 修饰的函数不能改变函数的成员变量 const Ds *const this;
        if(fa[x] != x) fa[x] = find(fa[x]);
        return fa[x];
    }
};

//但是可以加上mutable
```


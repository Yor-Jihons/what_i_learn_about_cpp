# C++で学んだこと

## 1. キャスト系

### 1.1. static_cast

int型からdouble型, int型からlong型のように**コンパイラが推測しやすい**強制的な型変換に使う。

### 1.2. dynamic_cast

親クラスで保持しているオブジェクトを子クラスとして見なしてキャストする場合に使う。
ただし、基本的にこのキャストを行う場合は設計自体がミスしている可能性が高い。

```C++
Parent* parent = new Child();
Child* child   = dynamic_cast<Child*>(parent); // ← Parentで保持しているオブジェクトをChildとして見なす
```

### 1.3. const_cast

const付きのデータからconstを外すためのキャスト。

### 1.4. reinterpret_cast

[キャスト - プログラマーズ雑記帳][1]によるとstatic_castを使うケースでもなく
dynamic_castを使うケースでもない場合に使うらしい。

1. ポインタのアドレス値をint型変数に格納する場合
2. プリミティブ型のポインタ同士の変換( int* → double* )

### 参考文献

[キャスト - プログラマーズ雑記帳][1]

[1]: http://yohshiy.blog.fc2.com/blog-category-9.html

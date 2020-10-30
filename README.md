# 一般的な Java 命名ルール

## 変数

### 変数名
変数名は、「頭文字が小文字のキャメルケース（Camel Case）」となる。頭文字が小文字で、複数の単語を組み合わせてメソッド名を構成する場合は、各単語の先頭を大文字にする（変数名と同じ形式）。

```console
userName
```
```java
private String userName = "Mike";
```

### 定数名
定数名はすべて大文字とする。複数の単語を組み合わせて構成する場合は、各単語の間を '_'（アンダースコア）で区切る。
```console
MAX_VALUE
```
```java
public static final int MAX_VALUE = 100;
```

### ループカウンタ変数
スコープの狭いループ変数は、'i', 'j', 'k' ... を利用する。通常の処理や、スコープの広いループでは、このような命名の変数は使わないようにする。
```java
for (int i = 0; i < ROW_MAX; i++) {
    for (int j = 0; j < COLUMN_MAX; j++) {
        for (int k =0; k < FIELD_SIZE; k++) {
            // body
        }
    }

}
```

## メソッド
### メソッド名
メソッド名は、「頭文字が小文字のキャメルケース（Camel Case）」となる。頭文字が小文字で、複数の単語を組み合わせてメソッド名を構成する場合は、各単語の先頭を大文字にする（変数名と同じ形式）。
```console
updateEmplyees()
```
```java
public int updateEmplyees(Employee employee) {
    // body
}
```

### ファクトリメソッド名
ファクトリメソッド（インスタンスを生成するメソッド）名は、メソッド名の先頭に 'create' をつけ、その後ろにメソッドで生成するオブジェクト名を続ける。
```console
createCars()
```
```java
public List<Car>  createCars() {
    // body
}
```

### true/false を返却するメソッド名
boolean 変数を返却するメソッド名は戻り値の状態が判断できる名前を付ける。メソッド名の先頭に 'is'、'can'、'has' などを付けて、「～か」というような疑問文になるようなメソッド名を付け、変数の中身が直感的に想像できるような名前にする。

たとえば、'isEmpty()' だったら「空っぽか？」となるので、true だったら「空です」となり、false だったら「空じゃない」です、となる。
```console
isEmpty()
```
```java
public boolean isEmpty() {
    // body
}
```

## パッケージ

### パッケージ名

パッケージ名は、ドット '.' で区切った文字列で定義し、基本的には英小文字を使用する。

パッケージの機能が判断できる名前を使用し、単語の短縮系は極力避ける。

```java
package jp.co.domainname.projectname.framework;
```

## クラス関連

### クラス名

クラス名は先頭文字を大文字にする。複数の単語を組み合わせて構成する場合は、各単語の先頭を大文字にする。

```java
public class App {
    // body
}
```

### 例外クラス名

例外クラスは、クラス名の最後に 'Exception' を付ける。

```java
public class AppException extends Exception {
    // body
}
```

非チェック例外の場合は、'RuntimeException' と付けて、チェック例外と区別できるようにする。

```java
public class AppRuntimeException extends RuntimeException {
    // body
}
```

### インタフェース名

インタフェース名はクラス名と同じように命名すれば良いが、よくあるインタフェース名の付け方としては、先頭に 'I' を付ける方法がある。

```java
public interface IPrinter {
    // body
}
```

### 実装クラス名

また特定のインターフェースを実装していることを明示したいクラスには、クラス名の末尾に 'Impl' を付けるパターンをよく見かける。

```java
public class PdfPrinterImpl implements IPrinter {
    // body
}
```

### 抽象クラス名

抽象クラス名もクラス名と同じように命名すれば良い。明示的に抽象クラスだということを示したい場合は、クラス名の先頭に 'Abstract' を付けるのがよく見かけるパターンである。

```java
public abstract class Abstract Player {
    // body
}
```

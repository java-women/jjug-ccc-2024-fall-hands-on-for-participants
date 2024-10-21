# ハンズオン Part2
## JShell
Preview Featuresで起動

```shell
$ jshell --enable-preview
```

終了

```
jshell> /exit
```

JShellでHello Worldを出力する

```
jshell> System.out.println("Hello World!")
```

<details>
<summary>(余裕があれば) "Hello Javajo!"の入力後に「$◯」が表示されるのでそれを入力してみよう！</summary>

```
jshell> "Hello Javajo!"
jshell> $◯
```

</details>

## var
文字列を出力する  
varを使った書き方に書き換えてみよう！

```java
String hello = "Hello World!";
System.out.println(hello);
```

<details>
<summary>(余裕があれば) 初期化時に値の宣言をしないとエラーになることを確認する</summary>

```
jshell> var obj1
```

</details>

<details>
<summary>(余裕があれば) nullで初期化するとエラーになることを確認する</summary>

```
jshell> var obj2 = null
```

</details>

ローカル変数でのみ使用可能  
以下のソースコードをjshellで打ってみて、エラー箇所を確認して修正してみよう！

```java
class Sample {
    var hoge = "hoge";
        
    void sample() {
        var fuga = "fuga";
    }
}
```

## Text Blocks
Text Blocksで変数を定義し、出力した時に整形されていることを確認する

```java
String html = """
              <html>
                  <body>
                      <p>Hello, world</p>
                  </body>
              </html>
              """;
System.out.println(html);
```


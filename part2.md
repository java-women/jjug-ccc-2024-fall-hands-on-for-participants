# ハンズオン Part2
## JShell
起動

```shell
$ jshell
```

終了

```
jshell> /exit
```

JShellでHello Worldを出力する

```
jshell> System.out.println("Hello World!")
```

"Hello Javajo!"の入力後に「$◯」が表示されるのでそれを入力してみよう！

```
jshell> "Hello Javajo!"
jshell> $◯
```

## var
文字列を出力する
varを使った書き方に書き換えてみよう！

```java
String hello = "Hello World!";
System.out.println(hello);
```

初期化時に値の宣言をしないとエラーになることを確認する

```
jshell> var obj1
```

nullで初期化するとエラーになることを確認する

```
jshell> var obj2 = null
```

ローカル変数でのみ使用可能
以下のソースコードを打ってみて、エラー箇所を修正してみよう！

```
jshell> class Sample {
    var hoge = "hoge";
        
    void sample() {
        var fuga = "fuga";
    }
}
```

## Text Blocks
Text Blocksで変数を定義し、出力した時に整形されていることを確認する

```
jshell> String html = """
                      <html>
                          <body>
                              <p>Hello, world</p>
                          </body>
                      </html>
                      """
jshell> System.out.println(html)
```


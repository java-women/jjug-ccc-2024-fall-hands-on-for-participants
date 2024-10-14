# Records

##　　名前と年齢と住所を持った人を表すオブジェクトを書いてみよう！
### レコードクラスを作る
```java
public record Person(String name, int age, String address) {}
```
### インスタンスの自動生成
```java
var marika = new Person("marika",34,"Tokyo");
```
### フィールドへのsetter禁止
```java
marika.setName("Shiotsuki");
// error
|  エラー:
|  シンボルを見つけられません
|    シンボル:   メソッド setName(java.lang.String)
|    場所: タイプPersonの変数 marika
|  marika.setName("Shiotsuki");
|  ^------------^
```
### フィールドのgetter生成
```java
marika.age();
// result
$3 ==> 34
```
### toString()メソッドの自動実装
```java
System.out.println(marika); 
// result
$4 ==> Person[name=marika, age=34, address=Tokyo]
```
### (additional) レコード型かの確認
```java
System.out.println(Person.class.isRecord()); 
// result
$5 ==> true
```
### (additional) レコード型におけるフィールドの形取得
```java
var components = Person.class.getRecordComponents();
for (var component : components) {
    System.out.println(component.getName() + ": " + component.getType().getSimpleName());
}
// result
$6 ==> name: String
$7 ==> age: int
$8 ==> address: String
```

# Switch

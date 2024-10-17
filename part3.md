# Records

##　　名前と年齢と住所を持った人を表すオブジェクトを書いてみよう！
### これまで
```java
public class Person {
    private final String name;
    private final int age;
    private final String address;

    public Person(String name, int age, String address) {
        this.name = name;
        this.age = age;
        this.address = address;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    public String getAddress() {
        return address;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Person person = (Person) o;
        return age == person.age &&
               Objects.equals(name, person.name) &&
               Objects.equals(address, person.address);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name, age, address);
    }

    @Override
    public String toString() {
        return "Person{" +
               "name='" + name + '\'' +
               ", age=" + age +
               ", address='" + address + '\'' +
               '}';
    }
}
```
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
## 以下のパターンを書いてみよう
①  “：” の代わりに使える “->”が登場。 自動的にbreak相当の動作をする。
②  複数の定数をカンマで区切って指定できる
③  複数行からなるブロックから値を返すyieldが追加になった
## ①と②と③はまとめて書いてみよう
```java
String getEmotion(String day) {
    return switch(day) {
    case MONDAY, TUESDAY, WEDNESDAY, THURSDAY -> "( ́Д`)";
    case FRIDAY                               -> "ヽ(・∀・)ノ";
    case SATURDAY, SUNDAY                     -> "ヽ(* ́∀`)ノ";
    default -> {
        System.out.println("未知の曜日です: " + day);
        yield "(-_-)";
    }
    };
}
```
```java
System.out.println(getEmotion("MONDAY"));
// result
$1 ==> ( ́Д`)
```
```java
System.out.println(getEmotion("FRIDAY"));
// result  
$2 ==> ヽ(・∀・)ノ
```
```java
System.out.println(getEmotion("EVERYDAY"));
// result
$3 ==> 未知の曜日です: EVERYDAY
$4 ==> (-_-)
```

もっと追加した方がいいと思う。
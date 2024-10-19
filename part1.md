# Launch Multi-File Source-Code Programs

## JEP 330 Launch Single-File Source-Code Programs
* 前提
    - JEP330 では 1 つのファイルに収める必要がある。

* [`Prog.java`](/part1/JEP330/Prog.java) 

   ``` java
    class Prog {
        public static void main(String[] args) {
            Helper.run();
        }
    }
    class Helper {
      static void run() { 
          System.out.println("Hello!");
      }
    }
   ```

* 実行(実行前には、当資料のあるフォルダに移動しておいてください。)
    ```
    $ cd part1/JEP330
    $ java Prog.java
    ```

    > [NOTE] これまでのJavaでは、javacコマンドでコンパイル後、実行時はjava ${クラス名}でしたが、　新しくなってからはjava ${クラス名}.java だけでコンパイルと実行ができるようになります。

* 実行結果
    ```
    Hello!
    ```


## JEP 458 Launch Multi-File Source-Code Programs
* 前提
    - 複数のソースコードから構成される Java プログラムのすべてのファイルを事前にコンパイルしなくとも、java コマンドで直接実行すると実行時に必要に応じてコンパイルし、実行できる。

* [`Prog.java`](/part1/JEP458/Prog.java)
    ``` java
    class Prog {
        public static void main(String[] args) {
            Helper.run();
        }
    }
    ```

* [`Helper.java`](/part1/JEP458/Helper.java)
    ``` java
    class Helper {
      static void run() { 
          System.out.println("Hello!");
      }
    }
    ```

* 実行
    ```
    $ cd ..
    $ cd part1/JEP458
    $ java Prog.java
    ```

* 実行結果
    ```
    Hello!
    ```



# Implicitly Declared Classes and Instance Main Methods
## Hello World
* [HelloWorld.java](/part1/HelloWorld.java)
    ``` java
    void main() {
        println("HelloWorld");  
    }
    ```

* 実行
    ```
    $ cd ..
    ## java 23以上をインストールしている場合
    $ java HelloWorld.java 
    ## java 23-ea 等、リリース前のバージョンを利用している場合
    $ java --enable-preview HelloWorld.java
    ```

* 実行結果
    ```
    HelloWorld
    ```

### Console
* [Console.java](/part1/Console.java)
    ``` java
    void main() {
        String name = readln("Name: ");
        print("Pleased to meet you, ");
        println(name);
    }
    ```

* 実行
    ```
    ## java 23以上をインストールしている場合
    $ java Console.java
    ## java 23-ea 等、リリース前のバージョンを利用している場合
    $ java --enable-preview Console.java
    ```

* 実行結果
    ```
    Name: (対話形式で聞かれるので何か入力する)
    Pleased to meet you, (入力した内容が出る)
    ```

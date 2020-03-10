# Untitled

## JDK\(Java Development Kit,Java开发工具包\)

-包含了Java的开发工具包括JRE -用于开发Java

## JRE\(Java Runtime Environment,Java运行环境\)。

-包含了JVM和核心类库 -用于运行Java

## JVM的内存模型

![JVM&#x5185;&#x5B58;&#x6A21;&#x578B;](https://upload-images.jianshu.io/upload_images/8007735-43916b0e82d8eaec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 引用对象：

值保存在堆中，栈存的是对象的地址

```text
Person p = new Person()；
```

先在堆中new一个Person\(\) 的对象 而p在栈中，存着对象的地址（间接寻址）

```text
public class test {
    public int a;
｝
public class output {
    public static void swap(test t1){
        t1.a = 6;
        System.out.println("调用方法后的t1的值："+t1.a);
    }
    public static void main(String[] args) {
        test test   = new test();
        System.out.println("生成的t1的值："+test.a);
        swap(test);
        System.out.println("最终值："+test.a);
```

![&#x5F15;&#x7528;&#x5BF9;&#x8C61;&#x53C2;&#x6570;&#x4F20;&#x9012;](https://upload-images.jianshu.io/upload_images/8007735-7f47385ffc9d6b7d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

1.首先先在堆中开辟出一个new test（）对象，在栈中开辟出一块内存test（地址1）储存对象的地址。 2.调用swap方法，把new test（）对象中的值复制到（地址2），（）地址1）和（地址2）都引用的堆中对象的值

### 基本数据类型：

值保存在栈中

```text
int i = 1;
```

1保存在栈中，存的是i的地址，i在堆中

## 方法参数传递的过程

```text
public class test {
    public static void swap(int i){
        i = 6;
        System.out.println(i);
    }

    public static void main(String[] args) {
        int a= 0;
        test.swap(a);
        System.out.println(a);
    }
}
```

1.先执行int a = 0;在栈中开辟出一块内存（地址1），存入0 2.然后调用swap方法再开辟出一块内存（地址2），将（地址1）的值复制到（地址2）即0. 3.方法内部6覆盖了（地址2）中的值


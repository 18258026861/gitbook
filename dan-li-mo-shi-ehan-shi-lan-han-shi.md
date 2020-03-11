# 单例模式-恶汉式，懒汉式

## 单例模式适用于创建对象消耗大量资源，所以只创建一个对象

## 懒汉和恶汉的区别，什么时候new对象

### 恶汉式：先创建

```text
public class lazy {

    private  lazy(){

    }
     private  static lazy l1 = null;//刚开始不创建

    public static lazy getLazy(){
        String s = "";
        if(l1 == null){//判断有没有被创建
            s = "创建懒汉1";
            l1 = new lazy();

        }
        System.out.println(s);
        return l1;
    }

}

public class main {
    public static void main(String[] args) {
       lazy l1 = lazy.getLazy();
        lazy l2 = lazy.getLazy();
        lazy l3 = lazy.getLazy();
}
```



![&#x6076;&#x6C49;&#x5F0F;](.gitbook/assets/tu-pian%20%281%29.png)

——————————————————————————————————————————————————

### 懒汉式：最开始不创建对象，知道有人调用了再创建，之后的人都使用这个对象

```text
public class lazy {

    private  lazy(){

    }
     private  static lazy lazy = null;//刚开始不创建

    public static lazy getLazy(){
        if(lazy == null){//判断有没有被创建
            lazy = new lazy();
        }
        return lazy;
    }

}
```




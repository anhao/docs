# Java 代码块

>在程序中 使用`{}`定义就是代码块，代码块出现的文字以及定义分为普通代码块，构造代码块，静态代码块
>
>执行顺序为：静态代码块-》普通代码块-》构造代码块
>
>实例化类就会自动执行这些代码块，**其中静态代码块只执行一次**，

## 普通代码块

> 类中的普通代码块就是 在类中直接添加一个`{}`代码块，不用加其他修饰符,也可以在方法里面加普通代码块!

```java
public class Demo{
    String name = "Anhao";
    {
        name = "Alone88";
        Sysotem.out.println("普通代码块"+name);
    }
    public static void main(String[] args){
        new Demo();
    }
}


```

//输出

```java
普通代码块Alone88
```



## 构造代码块

> 构造代码块就是定义的构造函数,构造函数就是方法名和类名一样，不需要返回值，可以定义多个构造方法

```java
public class Demo{
    public Demo(){
        Sysotem.out.println("构造代码块");
    }
    public static void main(String[] args){
        new Demo();
    }
}
```

输出：

```java
构造代码块
```





## 静态代码块

> 静态代码块优先级最高，不管有多少个实例化对象出现，都只执行第一次

```java

public class Demo{
    static{
        Sysotem.out.println("静态代码块");
    }
    public static void main(String[] args){
        new Demo();
    }
}
```

输出：

```
静态代码块
```


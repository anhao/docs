# ThinkPHP 之 Facade 

门面为容器中的类提供了一个静态调用接口，相比于传统的静态方法调用，	带来了更好的可测试性和扩展性，你可以为任何的非静态类库定义一个 facade 类。

**Facade功能 让类无需实例化而直接进行静态方式调用**



## 示例



### 创建一个公共方法 

创建一个` app\common\Test`方法

```php
<?php
namespace app\common;

class Test{

    public function Hello(){
        return 'Hello';
    }
}
   
```

正常我们调用这个方法应该是这样的

```php	
<?php 

    $test = new \app\common\Test;
	echo $test->Hello();
?>
```

### 创建一个静态代理类 Facade

创建一个Facade代理类 `app\facade\Test` 这个类名不一定需要和 Test 类一样

```php
<?php

namespace app\facade;
class Test extends \think\facade{
    
    protected static function getFacadeClass(){
        return '\app\common\Test';
    }
}
    
>
```

创建代理之后就可以在控制器里面直接用facade 来静态调用Test类了

```php
<?php
    
namespace app\controller;
use app\facade\Test;
class Demo{
    public function getFacade(){
        return Test::Hello(); //这样就静态调用了Test类的Hello方法
    }
}
```

#### 动态绑定

```php
 public function bindFacade(){

        // 动态绑定facade
        //  如果没有在静态代理类中显示要绑定的类名，就需要动态绑定facade
        // 就是没有在静态代理类中使用 getFacadeClass，就需要动态绑定
        \think\facade::bind('app\facade\Test','app\common\Test');
        return \app\facade\Test::Hello();
    }
```


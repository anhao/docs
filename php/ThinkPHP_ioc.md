# ThinkPHP 依赖注入

一般来说控制器里面的方法只能接收URL传过来的字符串，数值等数据，

怎么向方法里面传递对象呢？就要用到依赖注入了



###  被注入的对象

```php
<?php 
    /**
    * 要被注入的对象
    */
namespace app\common;
    
    class Temp{
    public $name;
    
    public function __construct($name="Alone88"){
        $this->name = $name;
    }
    public function setName($name){
        $this->name = $name;
    }
    
   public function getName(){
       return $this->name;
}
}
    
?>
```



### 要注入的控制器

```php

<?php
    /**
    * 控制器
    */
    
    namespace app\index\controller;

	class Demo{
        //参数列表里面注入对象
        public function getMethod(\app\common\Temp $temp){
            // \app\common\Temp $temp 等于下面一句
            // $temp  = new \app\common\Temp;
            
            //这样就可以获取注入对象的方法了
            return $temp->getName();
        }
    }
    ?>

```



###	绑定类 和 闭包 到容器
```php
<?php
    /**
    * 控制器
    */
    namespace app\index\controller;
    
    class Demo{
        //参数列表里面注入对象
        public function bindClass(){
        	//通过助手函数
        	bind('temp','\app\admin\common\Temp');
        	$temp = app('temp',['name'=>'Anhao']);
        	
        	//通过命名空间
        	\think\container::set('temp1','app\admin\common\Temp');
        	$temp1 = \think\container::get('temp1',['name'=>'anhao']);
        	
        	return $temp->getName();
        }
        
        //绑定一个闭包到容器；闭包就相当于匿名函数
        public function bindClosure(){
            \think\container::set('demo',function($site){
                return $site;
            });
            return \think\container::get('demo',['site'=>'Alone88']);
        }
    }
    ?>
```
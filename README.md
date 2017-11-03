PHPMOCK，是一个生成MOCK模拟数据的PHP类库，目前已应用于[PHPRAP](http://phprap.gouguoyin.cn/)项目中；
## 使用
#### 引入类
 
 ```php
  include_once($_SERVER['DOCUMENT_ROOT']."/mock.php");
 ```
     
#### 实例化类
 
 ```php
  $mock = new mock();
 ```
 
#### 常用方法
 
#### 1. string:生成随机字符串
    
- string(number):从默认字符串(abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789)里返回number个随机字符

    ```php
    示例：$mock->string(2);
    ```
     
    ```php
    返回：af或Bf或2f或0H或81
    ```
- string(number, string):从指定字符串string里返回number个随机字符

    ```php
    示例：$mock->string(2, 'gouguoyin');
    ```
     
    ```php
    返回：gg或ui或ng
    ```
         
- string(min-max):从默认字符串(abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789)里返回min-max个随机字符

    ```php
    示例：$mock->string('1-3');
    ```
     
    ```php
    返回：SHN或WS或81或1或a
    ```
- string(min-max, strings):从指定字符串里返回min-max个随机字符

    ```php
    示例：$mock->string('1-3', 'gouguoyin');
    ```
     
    ```php
    返回：n或uo或ogy
    ```    
##### 2. number:生成随机数字
    
- number(number):从默认数字(0123456789)里返回number个随机数字

    ```php
    示例：$mock->number(4);
    ```
     
    ```php
    返回：7559或0729
    ```
- number(number, numbers):从指定数字里返回number个随机数字

    ```php
    示例：$mock->number(4, '56789');
    ```
     
    ```php
    返回：5855或7659
    ```
- number(min-max):从默认数字(0123456789)里返回min-max个随机数字

    ```php
    示例：$mock->number('3-5');
    ```
     
    ```php
    返回：693或3594或01675
    ```
- number(min-max, numbers):从指定数字里返回min-max个随机数字

    ```php
    示例：$mock->number('2-4', '123456');
    ```
     
    ```php
    返回：63或251或6345
    ```      
##### 3. float:生成随机浮点型
    
- float(number, number)
- float(min-max, number)
- float(number, min-max)
- float(min-max, min-max)

##### 4. boolean:生成随机布尔值

- boolean():随机返回true或false

    ```php
    示例：$mock->boolean();
    ```
     
    ```php
    返回：true或false
    ```  
    
- boolean(0):返回false

    ```php
    示例：$mock->boolean(0);
    ```
     
    ```php
    返回：false
    ```  
    
- boolean(1):返回true

    ```php
    示例：$mock->boolean(1);
    ```
     
    ```php
    返回：true
    ```  
    

##### 5. arr:生成随机数组
    
## 联系

- 如果您在使用过程中有任何疑问，或有好的意见和想法，请通过以下途径联系我或者新建 [Issue](https://github.com/gouguoyin/phprap/issues)  讨论新特性或者变更。
- 官方网站：[phprap.gouguoyin.cn](http://phprap.gouguoyin.cn)
- 演示网站：[apidoc.gouguoyin.cn](http://apidoc.gouguoyin.cn)
- 作者博客：[www.gouguoyin.cn](http://www.gouguoyin.cn/about.html)
- 官方QQ群：421537504 <a style="margin-left:10px" target="_blank" href="http://shang.qq.com/wpa/qunwpa?idkey=d49826b55d1759513ce5d68253b3f0589b227587edf87059aa08125e620b73c0"><img border="0" src="http://pub.idqqimg.com/wpa/images/group.png" alt="GoPHP官方交流群" title="GoPHP官方交流群"></a>

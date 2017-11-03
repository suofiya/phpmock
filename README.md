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
    
- string(number, strings):从指定字符串strings里返回number个随机字符


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
    
- string(min-max, strings):从指定字符串strings里返回min-max个随机字符


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
    
- number(number, numbers):从指定数字numbers里返回number个随机数字


    ```php
    示例：$mock->number(4, '56789');
    ```
     
    ```php
    返回：5855或7659
    ```
    
- number(min-max):从min和max之间返回1个随机数字


    ```php
    示例：$mock->number('3-5');
    ```
     
    ```php
    返回：693或3594或01675
    ```    
      
##### 3. float:生成随机浮点型
    
- float(number, number):从默认数字(0123456789)中返回number个数字作为整数部分,从默认数字(0123456789)中返回number个数字作为小数部分


    ```php
    示例：$mock->float(3, 2);
    ```
     
    ```php
    返回：628.06或416.86或152.88
    ```
    
- float(min-max, number):从默认数字(0123456789)中返回min-max个数字作为整数部分,从默认数字(0123456789)中返回number个数字作为小数部分


    ```php
    示例：$mock->float('2-4', 2);
    ```
     
    ```php
    返回：78.96或987.38或9378.20
    ```
    
- float(number, min-max):从默认数字(0123456789)中返回number个数字作为整数部分,从默认数字(0123456789)中返回min-max个数字作为小数部分


    ```php
    示例：$mock->float(3, '2-3');
    ```
     
    ```php
    返回：196.32或202.285或083.66
    ```
    
- float(min-max, min-max):从默认数字(0123456789)中返回min-max个数字作为整数部分,从默认数字(0123456789)中返回min-max个数字作为小数部分


    ```php
    示例：$mock->float('2-3', '2-3');
    ```
     
    ```php
    返回：86.224或316.83或790.653或75.23
    ```
    
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

- arr(number, array):从指定数组array里返回number个随机数组


    ```php
    示例：$mock->arr(2, array('勾国印', '勾国磊', '张雨康', '张东川'));
    ```
     
    ```php
    返回：Array
       (
           [0] => 勾国磊
           [1] => 勾国印
       )
       或
       Array
       (
           [0] => 张雨康
           [1] => 勾国印
       )
    ```    
      
- arr(min-max, array):从指定数组array里返回min-max个随机数组

    
    ```php
    示例：$mock->arr('2-3', array('勾国印', '勾国磊', '张雨康', '张东川'));
    ```
   
    ```php
    返回：Array
     (
         [0] => 张雨康
         [1] => 勾国磊
     )
     或
     Array
     (
         [0] => 张东川
         [1] => 张雨康
         [2] => 勾国印
     )
    ```    
##### 5. object:生成随机对象

##### 6. price:生成随机价格

- price(number):从默认数字(0123456789)中返回number个数字作为整数部分,从默认数字(0123456789)中返回2个数字作为小数部分


    ```php
    示例：$mock->price(3);
    ```
         
    ```php
    返回：828.94或390.21
    ```   

- price(number, number):从默认数字(0123456789)中返回number个数字作为整数部分,从默认数字(0123456789)中返回number个数字作为小数部分


    ```php
    示例：$mock->price(2, 3);
    ```
         
    ```php
    返回：59.590或95.834
    ``` 
      
##### 7. date:生成随机日期、时间
    
- date()或date('Y-m-d H:i:s'):返回Y-m-d H:i:s格式时间


    ```php
    示例：$mock->date()或$mock->date('Y-m-d H:i:s');
    ```
         
    ```php
    返回：2017-11-03 11:21:30
    ```   
    
- date('Y-m-d'):返回Y-m-d格式日期


    ```php
    示例：$mock->date('Y-m-d');
    ```
         
    ```php
    返回：2017-11-03
    ```   
    
- date('H:i:s'):返回H:i:s格式时间


    ```php
    示例：$mock->date('H:i:s');
    ```
         
    ```php
    返回：11:21:30
    ```   
    
##### 8. color:生成随机颜色
    
- color()或color('hex'):返回十六进位制颜色 


    ```php
    示例：$mock->color()或$mock->color('hex');
    ```
         
    ```php
    返回：#9267a5或#d43367
    ```   
    
- color('rgb'):返回rgb格式颜色 


    ```php
    示例：$mock->color('rgb');
    ```
         
    ```php
    返回：rgb(253,58,51)或rgb(236,159,25)
    ```   
    
##### 9. email:生成随机邮箱
    
- email():返回随机邮箱


    ```php
    示例：$mock->email();
    ```
         
    ```php
    返回：6JznU1@yahoo.com或613824@qq.com或BSaXu8@163.com
    ```   
##### 10. mobile:生成随机手机号
    
- mobile():返回随机邮箱


    ```php
    示例：$mock->mobile();
    ```
         
    ```php
    返回：18624158057或13088904960或18273265934
    ```   
                                              
## 联系

- 如果您在使用过程中有任何疑问，或有好的意见和想法，请通过以下途径联系我或者新建 [Issue](https://github.com/gouguoyin/phprap/issues)  讨论新特性或者变更。
- 官方网站：[phprap.gouguoyin.cn](http://phprap.gouguoyin.cn)
- 演示网站：[apidoc.gouguoyin.cn](http://apidoc.gouguoyin.cn)
- 作者博客：[www.gouguoyin.cn](http://www.gouguoyin.cn/about.html)
- 官方QQ群：421537504 <a style="margin-left:10px" target="_blank" href="http://shang.qq.com/wpa/qunwpa?idkey=d49826b55d1759513ce5d68253b3f0589b227587edf87059aa08125e620b73c0"><img border="0" src="http://pub.idqqimg.com/wpa/images/group.png" alt="GoPHP官方交流群" title="GoPHP官方交流群"></a>



    

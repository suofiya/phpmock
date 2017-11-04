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
    
- *string(number)*:从默认字符串(abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789)里返回number个随机字符


    ```php
    示例：$mock->string(2);
    ```
     
    ```php
    返回：af或Bf或2f或0H或81
    ```
    
- *string(number, strings)*:从指定字符串strings里返回number个随机字符


    ```php
    示例：$mock->string(2, 'gouguoyin');
    ```
     
    ```php
    返回：gg或ui或ng
    ```
         
- *string(min-max)*:从默认字符串(abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789)里返回min-max个随机字符


    ```php
    示例：$mock->string('1-3');
    ```
     
    ```php
    返回：SHN或WS或81或1或a
    ```
    
- *string(min-max, strings)*:从指定字符串strings里返回min-max个随机字符


    ```php
    示例：$mock->string('1-3', 'gouguoyin');
    ```
     
    ```php
    返回：n或uo或ogy
    ```   
     
##### 2. number:生成随机数字
    
- *number(number)*:从默认数字(0123456789)里返回number个随机数字


    ```php
    示例：$mock->number(4);
    ```
     
    ```php
    返回：7559或0729
    ```
    
- *number(number, numbers)*:从指定数字numbers里返回number个随机数字


    ```php
    示例：$mock->number(4, '56789');
    ```
     
    ```php
    返回：5855或7659
    ```
    
- *number(min-max)*:从min和max之间返回1个随机数字


    ```php
    示例：$mock->number('10000-99999');
    ```
     
    ```php
    返回：94127或60658或14844
    ```    
      
##### 3. float:生成随机浮点型
    
- *float(number, number)*:从默认数字(0123456789)中返回number个数字作为整数部分,从默认数字(0123456789)中返回number个数字作为小数部分


    ```php
    示例：$mock->float(3, 2);
    ```
     
    ```php
    返回：628.06或416.86或152.88
    ```
    
- *float(min-max, number)*:从默认数字(0123456789)中返回min-max个数字作为整数部分,从默认数字(0123456789)中返回number个数字作为小数部分


    ```php
    示例：$mock->float('2-4', 2);
    ```
     
    ```php
    返回：78.96或987.38或9378.20
    ```
    
- *float(number, min-max)*:从默认数字(0123456789)中返回number个数字作为整数部分,从默认数字(0123456789)中返回min-max个数字作为小数部分


    ```php
    示例：$mock->float(3, '2-3');
    ```
     
    ```php
    返回：196.32或202.285或083.66
    ```
    
- *float(min-max, min-max)*:从默认数字(0123456789)中返回min-max个数字作为整数部分,从默认数字(0123456789)中返回min-max个数字作为小数部分


    ```php
    示例：$mock->float('2-3', '2-3');
    ```
     
    ```php
    返回：86.224或316.83或790.653或75.23
    ```
    
##### 4. boolean:生成随机布尔值

- *boolean()*:随机返回true或false


    ```php
    示例：$mock->boolean();
    ```
     
    ```php
    返回：`true`或`false`
    ```  
    
- *boolean(0)*:返回false


    ```php
    示例：$mock->boolean(0);
    ```
     
    ```php
    返回：`false`
    ```  
    
- *boolean(1)*:返回true


    ```php
    示例：$mock->boolean(1);
    ```
     
    ```php
    返回：`true`
    ```  
    
##### 5. arr:生成随机数组

- *arr(number, array)*:从指定数组array里返回number个随机数组


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
      
- *arr(min-max, array)*:从指定数组array里返回min-max个随机数组

    
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

- *price(number)*:从默认数字(0123456789)中返回number个数字作为整数部分,从默认数字(0123456789)中返回2个数字作为小数部分


    ```php
    示例：$mock->price(3);
    ```
         
    ```php
    返回：828.94或390.21
    ```   

- *price(number, number)*:从默认数字(0123456789)中返回number个数字作为整数部分,从默认数字(0123456789)中返回number个数字作为小数部分


    ```php
    示例：$mock->price(2, 3);
    ```
         
    ```php
    返回：59.590或95.834
    ``` 
      
##### 7. date:生成随机日期、时间
    
- *date()或date('Y-m-d H:i:s')*:返回Y-m-d H:i:s格式时间


    ```php
    示例：$mock->date()或$mock->date('Y-m-d H:i:s');
    ```
         
    ```php
    返回：2017-11-03 11:21:30
    ```   
    
- *date('Y-m-d')*:返回Y-m-d格式日期


    ```php
    示例：$mock->date('Y-m-d');
    ```
         
    ```php
    返回：2017-11-03
    ```   
    
- *date('H:i:s')*:返回H:i:s格式时间


    ```php
    示例：$mock->date('H:i:s');
    ```
         
    ```php
    返回：11:21:30
    ```   
    
##### 8. color:生成随机颜色
    
- *color()或color('hex')*:返回十六进位制颜色 


    ```php
    示例：$mock->color()或$mock->color('hex');
    ```
         
    ```php
    返回：#9267a5或#d43367
    ```   
    
- *color('rgb')*:返回rgb格式颜色 


    ```php
    示例：$mock->color('rgb');
    ```
         
    ```php
    返回：rgb(253,58,51)或rgb(236,159,25)
    ```   
    
##### 9. email:生成随机邮箱
    
- *email()*:返回随机邮箱


    ```php
    示例：$mock->email();
    ```
         
    ```php
    返回：`6JznU1@yahoo.com`或`613824@qq.com`或`BSaXu8@163.com`
    ```   
##### 10. url:生成随机网址
    
- *url()*:返回随机网址


    ```php
    示例：$mock->url();
    ```
         
    ```php
    返回：`https://www.taobao.com/9hcBLK.htm`或`https://www.gouguoyin.cn/GlSd6.asp`或`http://www.taobao.com/XmkPAgBt.html`
    ```  
- *url(protocols)*:从数组protocols中随机返回一个作为网址的协议部分


    ```php
    示例：$mock->url(array('http', 'https', 'ftp'));
    ```
         
    ```php
    返回：`ftp://www.taobao.com/qJd0.jsp`或`https://www.taobao.com/U2Z5Ly.html`或`https://www.baidu.com/NZKxm.json`
    ```  
- *url(array(), domains)*:从数组domains中随机返回一个作为网址的域名部分组成随机网址


    ```php
    示例：$mock->url(array(),array('www.gouguyin.cn', 'www.phprap.com', 'phprap.gouguoyin.cn'));
    ```
         
    ```php
    返回：`http://www.phprap.com/xiByQ2nm.json`或`http://www.gouguyin.cn/IzLc.asp`或`https://www.phprap.com/ZL1z8dIo.asp`
    ```  
- *url(array(), array(), suffixs)*:从数组suffixs中随机返回一个作为网址的后缀部分组成随机网址


    ```php
    示例：$mock->url(array(),array(),array('png', 'json', 'html'));
    ```
         
    ```php
    返回：`https://www.csdn.net/sFAXoRP.png`或`https://www.baidu.com/JZk0o.json`或`http://www.csdn.net/v7tFr.html`
    ```  
- *url(protocols, domains, suffixs)*:从数组protocols中随机返回一个作为网址的协议部分，从数组domains中随机返回一个作为网址的域名部分，从数组suffixs中随机返回一个作为网址的后缀部分组成随机网址


    ```php
    示例：$mock->url(array('http', 'https', 'ftp'),array('www.baidu.com', 'www.qq.com'),array('png', 'json', 'html'));
    ```
         
    ```php
    返回：`https://www.baidu.com/i6CU.json`或`https://www.qq.com/JhS1.json`或`ftp://www.baidu.com/d0eqESn.html`
    ```  
                                               
##### 11. mobile:生成随机手机号
    
- *mobile()*:返回随机邮箱


    ```php
    示例：$mock->mobile();
    ```
         
    ```php
    返回：`18624158057`或`13088904960`或`18273265934`
    ```   
    
##### 12. bank:生成随机银行
    
- *bank()或bank('title')*:返回随机银行名


    ```php
    示例：$mock->bank()或$mock->bank('title');
    ```
         
    ```php
    返回：`中国光大银行`或`交通银行`或`中国建设银行`
    ```   
    
- *bank('abbr')*:返回随机银行英文缩写


    ```php
    示例：$mock->bank('abbr');
    ```
         
    ```php
    返回：`CMBC`或`BOC`或`BCM`
    ```   
##### 13. country:返回随机国家
  
- *country()或country('title')*:返回随机国家名


    ```php
    示例：$mock->country()或$mock->country('title');
    ```
         
    ```php
    返回：`中国`或`美国`或`法国`
    ```  
- *country('abbr')*:返回随机国家英文缩写


    ```php
    示例：$mock->country('abbr');
    ```
         
    ```php
    返回：`CHN`或`USA`或`FRA`
    ```  
                
##### 14. region:返回随机区域
  
- *region()*:返回随机区域


    ```php
    示例：$mock->region();
    ```
         
    ```php
    返回：`华南`或`东北`或`华北`
    ```   
##### 15. province:返回随机省份
  
- *province()或province('title')*:返回随机省份名


    ```php
    示例：$mock->province()或$mock->province('title');
    ```
         
    ```php
    返回：`江苏省`或`浙江省`或`甘肃省`
    ```   
  
- *province('code')*:返回随机省份编码


    ```php
    示例：$mock->province('code');
    ```
         
    ```php
    返回：150000或410000或140000
    ```  
     
##### 16. city:返回随机城市   
 
- *city()或city('title')*:返回随机城市名


    ```php
    示例：$mock->city()或$mock->city('title');
    ```
         
    ```php
    返回：`天津市`或`上海市`或`南京市`
    ```   
 
- *city('code')*:返回随机城市编码


    ```php
    示例：$mock->city('code');
    ```
         
    ```php
    返回：640100或230100或440100
    ```   
     
##### 17. district:返回随机区县   
 
- *district()或district('title')*:返回随机区县名


    ```php
    示例：$mock->district()或$mock->district('title');
    ```
         
    ```php
    返回：`东城区`或`小店区`或`铁西区`
    ```   
 
- *district('code')*:返回随机区县编码


    ```php
    示例：$mock->district('code');
    ```
         
    ```php
    返回：110101或130102或210106
    ```   
    
##### 18. zip:返回随机邮编 

- *zip()*:返回随机邮编(v4)


    ```php
    示例：$mock->zip();
    ```
         
    ```php
    返回：860000或830068或450000
    ```
      
##### 19. ip:返回随机IP  
 
- *ip()*:返回随机IP(v4)


    ```php
    示例：$mock->ip();
    ```
         
    ```php
    返回：171.15.213.40或210.35.118.71或58.55.46.5
    ```   
##### 20. id_card:返回随机身份证号  
 
- *id_card()*:返回随机身份证号(中国大陆)


    ```php
    示例：$mock->id_card();
    ```
         
    ```php
    返回：`610401197006160288`或`511723195007018323`或`51068219601231677x`
    ```   
##### 21. cn_name:返回随机中文名字 
 
- *cn_name()*:返回随机中文名字 


    ```php
    示例：$mock->cn_name();
    ```
         
    ```php
    返回：`勾国印`或`张雨康`或`宇文哲敬`
    ```   
##### 22. en_name:返回随机英文名字 
 
- *en_name()*:返回随机英文名字 


    ```php
    示例：$mock->en_name();
    ```
         
    ```php
    返回：`gouguoyin`或`zhangyukang`或`shiwuhao`
    ```   
                                                                                                          
## 联系

- 如果您在使用过程中有任何疑问，或有好的意见和想法，请通过以下途径联系我或者新建 [Issue](https://github.com/gouguoyin/phprap/issues)  讨论新特性或者变更。
- PHPRAP：[phprap.gouguoyin.cn](http://phprap.gouguoyin.cn)
- 作者博客：[www.gouguoyin.cn](http://www.gouguoyin.cn/about.html)
- 官方QQ群：421537504 <a style="margin-left:10px" target="_blank" href="http://shang.qq.com/wpa/qunwpa?idkey=d49826b55d1759513ce5d68253b3f0589b227587edf87059aa08125e620b73c0"><img border="0" src="http://pub.idqqimg.com/wpa/images/group.png" alt="GoPHP官方交流群" title="GoPHP官方交流群"></a>



    

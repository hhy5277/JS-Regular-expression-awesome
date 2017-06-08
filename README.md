# JS-Regular-expression-awesome
:page_facing_up:我收藏的正则表达式大全，欢迎补充

## 验证微信号
微信账号仅支持6-20个字母、数字、下划线或减号，以字母开头
```js
/^[a-zA-Z]{1}[-_a-zA-Z0-9]{5,19}$/.test(value)
```

## 匹配腾讯QQ号码
```js
[1-9][0-9]{4,}
```

## JS替换字符串中的空格
```js
var reg = /([^\s])\s+([^\s\b])/g;
var str = " 中国  北京   朝阳区  df "; 
str = str.replace(reg, "$1%$2")
```

## 匹配Email地址
```js
[\w!#$%&'*+/=?^_`{|}~-]+(?:\.[\w!#$%&'*+/=?^_`{|}~-]+)*@(?:[\w](?:[\w-]*[\w])?\.)+[\w](?:[\w-]*[\w])?
```

## 匹配网址URL
```js
[a-zA-z]+://[^\s]*
```

## 匹配(年-月-日)格式日期
```
([0-9]{3}[1-9]|[0-9]{2}[1-9][0-9]{1}|[0-9]{1}[1-9][0-9]{2}|[1-9][0-9]{3})-(((0[13578]|1[02])-(0[1-9]|[12][0-9]|3[01]))|((0[469]|11)-(0[1-9]|[12][0-9]|30))|(02-(0[1-9]|[1][0-9]|2[0-8])))
```

## 匹配国内电话号码
```js
\d{3}-\d{8}|\d{4}-\{7,8}
```

## 检查手机号码：必须以数字开头，除数字外，可含有“-”
```js
//带中划线的手机号码：/^[+]{0,1}(d){1,3}[ ]?([-]?((d)|[ ]){1,12})+$/

//普通手机号码：/^1[34578]\d{9}$/
```

## 校验普通电话、传真号码：可以“+”开头，除数字外，可含有“-” 
```js
function isTel(s) { 
    var patrn=/^[+]{0,1}(d){1,3}[ ]?([-]?((d)|[ ]){1,12})+$/;
    if (!patrn.exec(s)) return false
    return true
}
```

## 配置中文字符
```js
[\u4e00-\u9fa5]
```

## 匹配18位身份证
身份证号码最后一位目前只有X
```js
/^(\d{6})(\d{4})(\d{2})(\d{2})(\d{3})([0-9]|X)$/
```

## 匹配中国邮政编码
```js
[1-9]\d{5}(?!\d)
```

## 检查是否是IP地址
```js
(25[0-5]|2[0-4]\d|[0-1]\d{2}|[1-9]?\d).(25[0-5]|2[0-4]\d|[0-1]\d{2}|[1-9]?\d).(25[0-5]|2[0-4]\d|[0-1]\d{2}|[1-9]?\d).(25[0-5]|2[0-4]\d|[0-1]\d{2}|[1-9]?\d)
```

## 不允许输入如下字符: (像 !@#$%^&* 等)
```js
var userName = $("#userRegistName").val(); 
var first = userName.charCodeAt(0); 
function CheckUserNameFormat(){
    if ((first>=65 && first <= 90)||(first>=97 && first <=122)){
    var pattern =/^[A-Za-z0-9_]+$/;  //首字母必须是A-Z或者a-z
    if(pattern.test(userName)){ 
         ......
    }
} 
```

## 匹配数字类型
```js
//匹配正整数
^[1-9]\d*$
//匹配负数
^-[1-9]\d*$
//正数
^-?[1-9]\d*$
//匹配非负正数（正整数 + 0）
^[1-9]\d*|0$
//匹配非正负数（负整数 + 0）
^-[1-9]\d*|0$
//匹配正浮点数
^[1-9]\d*\.\d*|0\.\d*[1-9]\d*$
//匹配负浮点数
^-[1-9]\d*\.\d*|-0\.\d*[1-9]\d*$
```

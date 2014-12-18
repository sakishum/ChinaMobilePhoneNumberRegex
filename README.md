ChinaMobilePhoneNumberRegex
===========================

目前国内网络上匹配手机号码的正则表达式很多都无法匹配最新的号码段，影响用户操作，故在此分享一个正则表达式来匹配中国大陆的手机号码段。

> 电信
> 
> 中国电信手机号码开头数字 2G/3G号段（CDMA2000网络）133、153、180、181、189 4G号段 177 联通
> 
> 中国联通手机号码开头数字 2G号段（GSM网络）130、131、132、155、156 3G上网卡145
> 3G号段（WCDMA网络）185、186 4G号段 176、185[1]  移动
> 
> 中国移动手机号码开头数字
> 2G号段（GSM网络）有134x（0-8）、135、136、137、138、139、150、151、152、158、159、182、183、184。
> 3G号段（TD-SCDMA网络）有157、187、188 3G上网卡 147 4G号段 178 补充
> 
> 14号段以前为上网卡专属号段，如中国联通的是145，中国移动的是147等等。 170号段为虚拟运营商专属号段，170号段的 11
> 位手机号前四位来区分基础运营商，其中 “1700” 为中国电信的转售号码标识，“1705” 为中国移动，“1709” 为中国联通。
> 
> 卫星通信 1349

以上内容来自[手机号码(百度百科)](http://baike.baidu.com/view/781667.htm)

去除 1349 无效号段以及已经淘汰的小灵通各号段，整理如下：   

```
130、131、132、133、134、135、136、137、138、139   
145、147   
150、151、152、153、155、156、157、158、159     
176、177、178、1700、1705、1709   
180、181、182、183、184、185、186、187、188、189   
```

正则表达式为：`(^(13\\d|14[57]|15[^4,\\D]|17[678]|18\\d)\\d{8}|170[059]\\d{7})$`。

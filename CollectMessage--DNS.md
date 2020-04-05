# 信息收集
## DNS 

-
-
```
root> nslookup  //解析出地址
> www.sina.com  //解析出地址
>
> set type=a    //只查a记录
>
> set type=mx   //只查mx记录 
>
> set type=ns   //域名服务器的地址
> 
> set type=ptr  //地址解析成为域名
> 
> set type=any  //所有
>
>
> text-->spf记录，将ip地址反向解析，做反垃圾邮件
>
>  //域名解析服务器
>  server 202.106.0.2
>  server 211.140.13.188
>  server 202.106.46.151
>  server 8.8.8.8    //谷歌域名服务器的地址
>
>
```
- nsiookup -q=any 163.com
- nslookup -q=any 163.com 114.114.114.114


## DNS信息收集---DIG

-
```
> dig www.sina.com
>
> dig www.sina.com any
>
> dig +noall +answer www.sina.com// 只看结果
>
> dig +noall +answer www.sina.com | awk '{print $5}'
>
> dig -x 220.181.14.157  //逆向查询
>
> dig +noall +answer txt chaos VERSION.BIND @ns1.sina.com.cn //BIND版本的查询
>
```

## DNS区域传输
-
```
>  dig @ns3.sina.com sina.com axfr
>
>  host -T -l sina.com ns3.sina.com
> 
> // 查询dpkg -L目录
> 
> fierce -dnsserver 8.8.8.8 -dns sina.com.cn -wordlist /usr/share/fierce/hosts.txt //暴力破解DNS


>  dnsenum -f /usr/share/dnsenum/dns.txt -dnsserver 8.8.8.8 sina.com -o sina.xml //暴力破解
>
> dnsmap sina.com -w /usr/share/dnsmap/wordlist_TLAs.txt
>
> whois sina.com  // 查询注册注册信息
> whosi 198.162.1.1  //地址查询注册查询
>
```





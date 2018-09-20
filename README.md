# CORS-Proxy-Server
代理转发 CORS 跨域资源请求

### 使用方法

1. 若是 `get` 请求,就在发生跨域的地方直接发送 `get` 请求,并把实际需要请求的地址 放到  `query` 中，参数名为: `remoteUrl` 
2. 若是 `post` 请求,就在发生跨域的地方直接发送 `post` 请求,并把实际需要请求的地址 放到  `query` 中，参数名为: `remoteUrl` 

#### 示例
 
代理服务地址为: `http://127.0.0.1:4500`
1. `get` 请求： 实际服务地址`remoteUrl` 为 `http://ip.taobao.com/service/getIpInfo.php?ip=myip` 

则请求的 `url` 格式为 `http://127.0.0.1:4500?remoteUrl=http://ip.taobao.com/service/getIpInfo.php?ip=myip`

2. `post` 请求 实际服务地址`remoteUrl` 为 `http://ip.taobao.com/service/getIpInfo2.php` ,`from` 表单的数据为 `ip=myip` 

则请求的url 格式为: `http://127.0.0.1:4500?remoteUrl=http://ip.taobao.com/service/getIpInfo2.php`

**其他参数和正常请求的格式一致**

>需要注意的是: 若是获取本地的`ip` ，经过该代理服务获取的 `ip` 就找不准确了
 

### Features

* 代理所有的方法请求
* 允许所有的`CORS`请求
* 代码层面支持 `https`

### 部署

1. `git clone git@github.com:jjeejj/CORS-Proxy-Server.git`
2. `npm install`
3. `npm run start`




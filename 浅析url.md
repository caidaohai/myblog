# 浅析url
url是Uniform Resource Locator（统一资源定位符）的简写，俗称为网页地址，简称网址，是因特网上标准的资源地址，如同网络上的门牌。它最初是由李爵士发明用来作为万维网的地址，现已被万维网联盟编制为因特网标准 [RFC1738](https://datatracker.ietf.org/doc/html/rfc1738)。

## url的标准格式
> \[协议类型\]://\[服务器地址\]:\[端口号\]/\[文件路径\]\[文件名\]?\[查询\]#锚点

比如："*https://zh.wikipedia.org:443/w/index.php?title=随机页面*" 其中
1. https 是协议;
2. zh.wikipedia.org，是服务器；
3. 443，是服务器上的网络端口号；
4. /w/index.php，是路径；
5. ?title=Special:随机页面，是询问。

## IP地址
IP地址（Internet Protocol Address）是指互联网协议地址，又译为网际协议地址。

IP地址是IP协议提供的一种统一的地址格式，它为互联网上的每一个网络和每一台主机分配一个逻辑地址。通过IP地址，保证用户在联网操作时，能够找到自己所需要的对象，使网络上的各种设备能够通过ip地址实现
互通

## 域名
域名（Domain Name），是由一串用点分隔的字符组成的互联网上某一台计算机或计算机组的名称，用于在数据传输时标识计算机的电子方位。域名可以说是一个IP地址的代称，目的是为了便于记忆后者。

### **顶级域**

顶级域（英语：Top-level domains，缩写：TLD）是域名中最高的一级，每个域名都以顶级域结尾。常见的顶域名如下
* .gov:政府相关的网站
* .edu:教育机构相关的网站
* .com:商业类网站
* .org:非营利组织
* .net:网络基础服务提供商
* .int:国际组织

### **子域名**

子域名将顶级域名进一步细分。域名层次结构中，顶级域名下面是二级域名，它位于顶级域名的左侧。例如，在zh.wikipedia.org中，wikipedia是二级域名。w3.org中，w3也是二级域名，与前例中的wikipedia属于一个层面。

二级域名下面是三级域名，它位于二级域名的左侧。例如，在zh.wikipedia.org中，zh是三级域名；zh-classical.wikipedia.org中，zh-classical也是三级域名，与前例中的zh属于一个层面。从右侧到左侧，隔一个点依次下降一层。

通常情况下，人们基于公司、产品或服务的名称来创建二级域名或更低级别的域名，以方便其他人识别和记忆。

完整域名的所有字符加起来不得超过253个ASCII字符的总长度。因此，当每一级都使用单个字符时，限制为127个级别：127个字符加上126个点的总长度为253。但实际上，某些域名可能具有其他限制；也没有只有一个字符的域名后缀。

## DNS
域名系统（英语：Domain Name System，缩写：DNS）是互联网的一项服务。它作为将域名和IP地址相互映射的一个分布式数据库，能够使人更方便地访问互联网。DNS使用TCP和UDP端口53。当前，对于每一级域名长度的限制是63个字符，域名总长度则不能超过253个字符。

nslookup程序探测域名的域名系统信息,知道域名对应的IP

比如 nslookup baidu.com

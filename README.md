# shadowsockes
亚马逊云服务器，推出免费使用12个月活动

准备工作（亚马逊账号+一张银行卡）

PS:谷歌云也有推出免费使用12个月的活动，但是国内的信用卡不能申请，本人手里只有一张招商银行young信用卡，所以做亚马逊云的教程
官网链接：aws.amazon.com

# 1.选择创建免费账户。

注册个人账户，而且我输入中文提示字符不对，只能改输入全英文
这里我使用的是信用卡，扣一美元预授权费用，借记卡没测试
# 2.账户创建完毕后，从控制台页面创建EC2实例。



这里我测试过rhel7.2和ubuntu16.04，发现ubuntu连接速度很快，不知道是不是错觉






此处生成rsa密钥，用来进行远程ssh链接使用，需配合putty使用

注意新增icmp规则打开ping和tcp:8388端口用来使用shadowsocks

# 3.远程ssh登录EC2实例。

实例启动后，请参照官网putty(菩提)教程ssh远程连接vps:

https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/putty.html?icmpid=docs_ec2_console
1).使用puttygen客户端将上面2.5生成的pem密钥导成putty密钥


2).使用putty客户端进行远程连接配置，需要配置两个部分




此处使用ubuntu@亚马逊EC2实例的公有DNS作为账户名，不同操作系统有不同的前缀



此处选择刚才由puttygen生成的putty密钥文件
# 4.远程连接成功后，以ubuntu为例：

   1),先"apt update"更新源

   2),apt安装python-pip

   3),pip安装shadowsocks


4),vim编辑shadowsocks.json

5),运行shadowsocks

然后一台shadowsocks服务器搭建成功，想使用请使用不同操作系统下面的shadowsocks客户端进行连接。

# 注意：切换root用户教程
sudo passwd root

# 注意：VPS搭建shadowsocks搭配谷歌bbr算法使用效果显著 
# 注意：在国内的用户使用kcptun效果更加显著
#2018-12-03更新           

亚马逊虽然是全球最大云计算提供商，但还是有几个缺点：  
1.每个月15G流量(后面发现谷歌也是1个月15G,只是由于YouTube是谷歌的产品，访问YouTube不计入流量)  
2.真的只有一年免费使用          
3.亚马逊云真的会扣1美元（谷歌扣了会退还）

经过两年的成长，我又有一张浦发银行的VISA信用卡，就可以完美的用谷歌云服务器了
原putty软件也升级成xshell神器    
谷歌云和亚马逊云创建服务器过程类似，安装shadowsocks也类似，过程略。  
谷歌云和亚马逊有个区别就是谷歌是可以选配机器的，可以自己调节cpu和内存，比如1核2.75G内存
谷歌是12个月到期或者赠送的300美元使用完就结束，双重判定。
但是谷歌有个惊天bug(or福利？)，就是一个人可以无限刷300美元的赠金。我已经用了第二个300美元的赠金了

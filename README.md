h248协议转sip,megaco协议转sip,固定电话转sip协议
H.248协议是 2000年由 ITU-T第 16工作组提出的媒体网关控制协议，它是在早期的MGCP协议基础上改进而成。H.248/MeGaCo协议是用于连接MGC与MG的网关控制协议，应用于媒体网关与软交换之间及软交换与 H.248/MeGaCo终端之间，是软交换应支持的重要协议。

目前在国内电信网络内，尤其是中国联通，大部分固话仍然采用H248协议。而当前的主流软交换平台却不支持H248协议，因为H248协议是mgc控制mg的网关控制协议，商业软交换是作为mgc来支持的。

SANGUMA公司的商业产品中有此模块，价格昂贵，国内应该是未曾见过。

H248协议前身为MGCP协议，而Asterisk其中有MGCP协议的模块，因此有人使用改模块简单修改后让其支持H248协议，但受限于Asterisk平台，单机并发几百线就会出现各类问题，无法进行商业大规模使用。


为了提高效率，本人写了一套只在信令层面进行与sip协议互转的网关平台，语音处理交给其他软交换例如vos等，这样最大限度的提高了可用性。协议转换网关具有以下特点：

1支持局方不开通反极信号条件下提供准确计费信号。反极信号是固话中实现准确计费的必要条件。如果局方不开通反极信号，目前世面上的o口网关，或其他协议转换设备，只能从开始拨号就认为是接通，从而无法准确计费，不能支持话批，ai机器人等业务。反极信号是之前模拟中继才有的业务，现在固话系统很多无法开通。本系统可达到反极信号同样效果。

2支持与vos,freeswitch等sip系统同机安装，节约硬件投资。也可独立安装。

3支持线路收敛，多地址，多光纤，多设备线路收敛到一台服务器上。

4接续速度快，o口网关使用音频信号传递拨号信息，接续过程需4-8秒，协议转换网关采用全数字流程，接续过程缩短到1秒以内。

5音频质量好。o口网关语音经过数字转模拟，模拟转数字2个过程，协议转换网关直接采用数字信号，中间不需要转换。

6并发高，单机可达3000线以上

7拒接功能，可全局配置拒接，呼入不占用线路资源。

---
{"dg-publish":true,"permalink":"/Tutorial/dnsmasq/","created":"2024-10-15T12:37:20.000+08:00","updated":"2024-10-27T18:23:50.897+08:00"}
---

## 极速版
- 
```
apt -y install dnsmasq
```
- 
```
nano /etc/dnsmasq.conf
```
然后输入分流规则
- 
```
echo -e "nameserver 1.1.1.1\nnameserver 8.8.8.8" > /etc/resolv.dnsmasq.conf
```
- 
```
chattr -i /etc/resolv.conf && echo -e "nameserver 127.0.0.1" > /etc/resolv.conf && chattr +i /etc/resolv.conf && /etc/init.d/dnsmasq restart
```


## 详细版
## 安装dnsmasq分流（确保53端口未被占用）
安装
```
apt -y install dnsmasq
```
卸载
```
sudo apt remove --purge -y dnsmasq && sudo apt autoremove -y && chattr -i /etc/resolv.conf && chmod 777 /etc/resolv.conf && echo -e "nameserver 1.1.1.1\nnameserver 8.8.8.8" > /etc/resolv.conf
```
## 编辑主配置文件
```
nano /etc/dnsmasq.conf
```
### 配置文件
```
# >指定 DNS 解析的配置文件
resolv-file=/etc/resolv.dnsmasq.conf

# >chatgpt
server=/browser-intake-datadoghq.com/38.181.72.14
server=/chat.openai.com.cdn.cloudflare.net/38.181.72.14
server=/gemini.google.com/38.181.72.14
server=/openai-api.arkoselabs.com/38.181.72.14
server=/openaicom-api-bdcpf8c6d2e9atf6.z01.azurefd.net/38.181.72.14
server=/openaicomproductionae4b.blob.core.windows.net/38.181.72.14
server=/production-openaicom-storage.azureedge.net/38.181.72.14
server=/static.cloudflareinsights.com/38.181.72.14
server=/.ai.com/38.181.72.14
server=/.algolia.net/38.181.72.14
server=/.api.statsig.com/38.181.72.14
server=/.auth0.com/38.181.72.14
server=/.chatgpt.com/38.181.72.14
server=/.chatgpt.livekit.cloud/38.181.72.14
server=/.client-api.arkoselabs.com/38.181.72.14
server=/.events.statsigapi.net/38.181.72.14
server=/.featuregates.org/38.181.72.14
server=/.host.livekit.cloud/38.181.72.14
server=/.identrust.com/38.181.72.14
server=/.intercom.io/38.181.72.14
server=/.intercomcdn.com/38.181.72.14
server=/.launchdarkly.com/38.181.72.14
server=/.oaistatic.com/38.181.72.14
server=/.oaiusercontent.com/38.181.72.14
server=/.observeit.net/38.181.72.14
server=/.openai.com/38.181.72.14
server=/.openaiapi-site.azureedge.net/38.181.72.14
server=/.openaicom.imgix.net/38.181.72.14
server=/.segment.io/38.181.72.14
server=/.sentry.io/38.181.72.14
server=/.stripe.com/38.181.72.14
server=/.turn.livekit.cloud/38.181.72.14
server=/openai/38.181.72.14
server=/24.199.123.28/32/38.181.72.14
server=/64.23.132.171/32/38.181.72.14
server=/20473/38.181.72.14


# >instagram
server=/achat-followers-instagram.com/103.214.22.32
server=/acheter-followers-instagram.com/103.214.22.32
server=/acheterdesfollowersinstagram.com/103.214.22.32
server=/acheterfollowersinstagram.com/103.214.22.32
server=/bookstagram.com/103.214.22.32
server=/carstagram.com/103.214.22.32
server=/cdninstagram.com/103.214.22.32
server=/chickstagram.com/103.214.22.32
server=/ig.me/103.214.22.32
server=/igcdn.com/103.214.22.32
server=/igsonar.com/103.214.22.32
server=/igtv.com/103.214.22.32
server=/imstagram.com/103.214.22.32
server=/imtagram.com/103.214.22.32
server=/instaadder.com/103.214.22.32
server=/instachecker.com/103.214.22.32
server=/instafallow.com/103.214.22.32
server=/instafollower.com/103.214.22.32
server=/instagainer.com/103.214.22.32
server=/instagda.com/103.214.22.32
server=/instagify.com/103.214.22.32
server=/instagmania.com/103.214.22.32
server=/instagor.com/103.214.22.32
server=/instagram-brand.com/103.214.22.32
server=/instagram-engineering.com/103.214.22.32
server=/instagram-help.com/103.214.22.32
server=/instagram-press.com/103.214.22.32
server=/instagram-press.net/103.214.22.32
server=/instagram.com/103.214.22.32
server=/instagramci.com/103.214.22.32
server=/instagramcn.com/103.214.22.32
server=/instagramdi.com/103.214.22.32
server=/instagramhashtags.net/103.214.22.32
server=/instagramhilecim.com/103.214.22.32
server=/instagramhilesi.org/103.214.22.32
server=/instagramium.com/103.214.22.32
server=/instagramizlenme.com/103.214.22.32
server=/instagramkusu.com/103.214.22.32
server=/instagramlogin.com/103.214.22.32
server=/instagramm.com/103.214.22.32
server=/instagramn.com/103.214.22.32
server=/instagrampartners.com/103.214.22.32
server=/instagramphoto.com/103.214.22.32
server=/instagramq.com/103.214.22.32
server=/instagramsepeti.com/103.214.22.32
server=/instagramtakipcisatinal.net/103.214.22.32
server=/instagramtakiphilesi.com/103.214.22.32
server=/instagramtips.com/103.214.22.32
server=/instagramtr.com/103.214.22.32
server=/instagran.com/103.214.22.32
server=/instagranm.com/103.214.22.32
server=/instagrem.com/103.214.22.32
server=/instagrm.com/103.214.22.32
server=/instagtram.com/103.214.22.32
server=/instagy.com/103.214.22.32
server=/instamgram.com/103.214.22.32
server=/instangram.com/103.214.22.32
server=/instanttelegram.com/103.214.22.32
server=/instaplayer.net/103.214.22.32
server=/instastyle.tv/103.214.22.32
server=/instgram.com/103.214.22.32
server=/intagram.com/103.214.22.32
server=/intagrm.com/103.214.22.32
server=/intgram.com/103.214.22.32
server=/kingstagram.com/103.214.22.32
server=/lnstagram-help.com/103.214.22.32
server=/theinstagramhack.com/103.214.22.32
server=/oninstagram.com/103.214.22.32
server=/online-instagram.com/103.214.22.32
server=/onlineinstagram.com/103.214.22.32
server=/web-instagram.net/103.214.22.32
server=/wwwinstagram.com/103.214.22.32

# >gemini
server=/ai.google.dev/103.214.22.32
server=/alkalimakersuite-pa.clients6.google.com/103.214.22.32
server=/makersuite.google.com/103.214.22.32
server=/bard.google.com/103.214.22.32
server=/deepmind.com/103.214.22.32
server=/deepmind.google/103.214.22.32
server=/gemini.google.com/103.214.22.32
server=/generativeai.google/103.214.22.32
server=/proactivebackend-pa.googleapis.com/103.214.22.32

# >bing
server=/bing.com/103.214.22.32
server=/bing.com.cn/103.214.22.32
server=/bing.net/103.214.22.32
server=/bing123.com/103.214.22.32
server=/bingads.com/103.214.22.32
server=/bingagencyawards.com/103.214.22.32
server=/bingapis.com/103.214.22.32
server=/bingapistatistics.com/103.214.22.32
server=/bingparachute.com/103.214.22.32
server=/bingsandbox.com/103.214.22.32
server=/bingvisualsearch.com/103.214.22.32
server=/bingworld.com/103.214.22.32
server=/bluehatnights.com/103.214.22.32
server=/dictate.ms/103.214.22.32
server=/flipwithsurface.com/103.214.22.32
server=/masalladeloslimites.com/103.214.22.32
server=/microsoft-give.com/103.214.22.32
server=/microsoftcloudsummit.com/103.214.22.32
server=/microsoftdiplomados.com/103.214.22.32
server=/microsoftlatamholiday.com/103.214.22.32
server=/microsoftmxfilantropia.com/103.214.22.32
server=/microsoftpartnersolutions.com/103.214.22.32
server=/msunlimitedcloudsummit.com/103.214.22.32
server=/office365love.com/103.214.22.32
server=/office365tw.com/103.214.22.32
server=/renovacionoffice.com/103.214.22.32
server=/sprinklesapp.com/103.214.22.32
server=/location.microsoft.com/103.214.22.32

# >Netflix
server=/fast.com/103.214.22.32
server=/netflix.ca/103.214.22.32
server=/netflix.com/103.214.22.32
server=/netflix.net/103.214.22.32
server=/netflixinvestor.com/103.214.22.32
server=/netflixtechblog.com/103.214.22.32
server=/nflxext.com/103.214.22.32
server=/nflximg.com/103.214.22.32
server=/nflximg.net/103.214.22.32
server=/nflxsearch.net/103.214.22.32
server=/nflxso.net/103.214.22.32
server=/nflxvideo.net/103.214.22.32
server=/netflixdnstest0.com/103.214.22.32
server=/netflixdnstest1.com/103.214.22.32
server=/netflixdnstest2.com/103.214.22.32
server=/netflixdnstest3.com/103.214.22.32
server=/netflixdnstest4.com/103.214.22.32
server=/netflixdnstest5.com/103.214.22.32
server=/netflixdnstest6.com/103.214.22.32
server=/netflixdnstest7.com/103.214.22.32
server=/netflixdnstest8.com/103.214.22.32
server=/netflixdnstest9.com/103.214.22.32
server=/netflixdnstest10.com/103.214.22.32
server=/netflix.com.edgesuite.net/103.214.22.32

# >disney
server=/abc/38.175.192.13
server=/bamtech/38.175.192.13
server=/espn/38.175.192.13
server=/hotstar/38.175.192.13
server=/marvel/38.175.192.13
server=/nationalgeographic/38.175.192.13
server=/starplus/38.175.192.13
server=/disney.asia/38.175.192.13
server=/disney.be/38.175.192.13
server=/disney.bg/38.175.192.13
server=/disney.ca/38.175.192.13
server=/disney.ch/38.175.192.13
server=/disney.co.il/38.175.192.13
server=/disney.co.jp/38.175.192.13
server=/disney.co.kr/38.175.192.13
server=/disney.co.th/38.175.192.13
server=/disney.co.uk/38.175.192.13
server=/disney.co.za/38.175.192.13
server=/disney.com/38.175.192.13
server=/disney.com.au/38.175.192.13
server=/disney.com.br/38.175.192.13
server=/disney.com.hk/38.175.192.13
server=/disney.com.tw/38.175.192.13
server=/disney.cz/38.175.192.13
server=/disney.de/38.175.192.13
server=/disney.dk/38.175.192.13
server=/disney.es/38.175.192.13
server=/disney.fi/38.175.192.13
server=/disney.fr/38.175.192.13
server=/disney.gr/38.175.192.13
server=/disney.hu/38.175.192.13
server=/disney.id/38.175.192.13
server=/disney.in/38.175.192.13
server=/disney.io/38.175.192.13
server=/disney.it/38.175.192.13
server=/disney.my/38.175.192.13
server=/disney.nl/38.175.192.13
server=/disney.no/38.175.192.13
server=/disney.ph/38.175.192.13
server=/disney.pl/38.175.192.13
server=/disney.pt/38.175.192.13
server=/disney.ro/38.175.192.13
server=/disney.ru/38.175.192.13
server=/disney.se/38.175.192.13
server=/disney.sg/38.175.192.13
server=/20thcenturystudios.com.au/38.175.192.13
server=/20thcenturystudios.com.br/38.175.192.13
server=/20thcenturystudios.jp/38.175.192.13
server=/adventuresbydisney.com/38.175.192.13
server=/babble.com/38.175.192.13
server=/babyzone.com/38.175.192.13
server=/bamgrid.com/38.175.192.13
server=/beautyandthebeastmusical.co.uk/38.175.192.13
server=/dilcdn.com/38.175.192.13
server=/disney-asia.com/38.175.192.13
server=/disney-discount.com/38.175.192.13
server=/disney-plus.net/38.175.192.13
server=/disney-portal.my.onetrust.com/38.175.192.13
server=/disney-studio.com/38.175.192.13
server=/disney-studio.net/38.175.192.13
server=/disney.my.sentry.io/38.175.192.13
server=/disneyadsales.com/38.175.192.13
server=/disneyarena.com/38.175.192.13
server=/disneyaulani.com/38.175.192.13
server=/disneybaby.com/38.175.192.13
server=/disneycareers.com/38.175.192.13
server=/disneychannelonstage.com/38.175.192.13
server=/disneychannelroadtrip.com/38.175.192.13
server=/disneycruisebrasil.com/38.175.192.13
server=/disneyenconcert.com/38.175.192.13
server=/disneyiejobs.com/38.175.192.13
server=/disneyinflight.com/38.175.192.13
server=/disneyinternational.com/38.175.192.13
server=/disneyinternationalhd.com/38.175.192.13
server=/disneyjunior.com/38.175.192.13
server=/disneyjuniortreataday.com/38.175.192.13
server=/disneylatino.com/38.175.192.13
server=/disneymagicmoments.co.il/38.175.192.13
server=/disneymagicmoments.co.uk/38.175.192.13
server=/disneymagicmoments.co.za/38.175.192.13
server=/disneymagicmoments.de/38.175.192.13
server=/disneymagicmoments.es/38.175.192.13
server=/disneymagicmoments.fr/38.175.192.13
server=/disneymagicmoments.gen.tr/38.175.192.13
server=/disneymagicmoments.gr/38.175.192.13
server=/disneymagicmoments.it/38.175.192.13
server=/disneymagicmoments.pl/38.175.192.13
server=/disneymagicmomentsme.com/38.175.192.13
server=/disneyme.com/38.175.192.13
server=/disneymeetingsandevents.com/38.175.192.13
server=/disneymovieinsiders.com/38.175.192.13
server=/disneymusicpromotion.com/38.175.192.13
server=/disneynewseries.com/38.175.192.13
server=/disneynow.com/38.175.192.13
server=/disneypeoplesurveys.com/38.175.192.13
server=/disneyplus.bn5x.net/38.175.192.13
server=/disneyplus.com/38.175.192.13
server=/disneyplus.com.ssl.sc.omtrdc.net/38.175.192.13
server=/disneyredirects.com/38.175.192.13
server=/disneysrivieraresort.com/38.175.192.13
server=/disneystore.com/38.175.192.13
server=/disneystreaming.com/38.175.192.13
server=/disneysubscription.com/38.175.192.13
server=/disneytickets.co.uk/38.175.192.13
server=/disneyturkiye.com.tr/38.175.192.13
server=/disneytvajobs.com/38.175.192.13
server=/disneyworld-go.com/38.175.192.13
server=/dssott.com/38.175.192.13
server=/go-disneyworldgo.com/38.175.192.13
server=/go.com/38.175.192.13
server=/mickey.tv/38.175.192.13
server=/moviesanywhere.com/38.175.192.13
server=/nomadlandmovie.ch/38.175.192.13
server=/playmation.com/38.175.192.13
server=/shopdisney.com/38.175.192.13
server=/shops-disney.com/38.175.192.13
server=/sorcerersarena.com/38.175.192.13
server=/spaindisney.com/38.175.192.13
server=/star-brasil.com/38.175.192.13
server=/star-latam.com/38.175.192.13
server=/starwars.com/38.175.192.13
server=/starwarsgalacticstarcruiser.com/38.175.192.13
server=/starwarskids.com/38.175.192.13
server=/streamingdisney.net/38.175.192.13
server=/thestationbymaker.com/38.175.192.13
server=/thisispolaris.com/38.175.192.13
server=/watchdisneyfe.com/38.175.192.13
```


## 配置文件上游dns服务器列表
方法一：一步到位
```
echo -e "nameserver 1.1.1.1\nnameserver 8.8.8.8" > /etc/resolv.dnsmasq.conf
```
方法二：分步
```
nano /etc/resolv.dnsmasq.conf
```

```
nameserver 1.1.1.1
nameserver 8.8.8.8 
```
-  遇到标注域名走解锁DNS，其余走1.1.1.1和8.8.8.8DNS
## 将dnsmasq作为系统DNS服务器
```
chattr -i /etc/resolv.conf && echo -e "nameserver 127.0.0.1" > /etc/resolv.conf && chattr +i /etc/resolv.conf
```
- 解除 /etc/resolv.conf 的不可修改属性，使文件可编辑。
- 将 nameserver 127.0.0.1 写入 /etc/resolv.conf，替换文件内容。
- 将 /etc/resolv.conf 设置为不可修改状态，防止后续更改。

（非必要步骤） 若提示/etc/resolv.conf为符号链接，则删除 /etc/resolv.conf 符号链接，并创建一个新的静态文件：
`rm /etc/resolv.conf`
`echo -e "nameserver 127.0.0.1" > /etc/resolv.conf

（非必要步骤）如果本地已经启动相关的DNS解析配置工具，先停用相关守护进程，释放53端口
停止systemd-resolved和resolvconf
```
systemctl stop systemd-resolved && systemctl disable systemd-resolved && systemctl stop resolvconf && systemctl disable resolvconf
```
## 重启dnsmasq
```
/etc/init.d/dnsmasq restart
```
## 检验
```
apt-get -y install dnsutils
```

```
nslookup chatgpt.com dns服务器地址
```

## 解锁机脚本
https://github.com/myxuchangbin/dnsmasq_sniproxy_install
解锁机上安装sniproxy
```
wget --no-check-certificate -O dnsmasq_sniproxy.sh https://raw.githubusercontent.com/nanci0406/dnsmasq_sniproxy_install/master/dnsmasq_sniproxy.sh && bash dnsmasq_sniproxy.sh -fs
```
安装iptables
```
apt -y install iptables
```
阻止其他 IP 访问 DNS 服务
```
iptables -A INPUT -p udp --dport 53 -j DROP && iptables -A INPUT -p tcp --dport 53 -j DROP
```
允许特定IP地址通过UDP和TCP端口53的流量
```
iptables -I INPUT 1 -p udp -s 新的放行ip --dport 53 -j ACCEPT && iptables -I INPUT 1 -p tcp -s 新的放行ip --dport 53 -j ACCEPT
```

```
iptables -I INPUT 1 -p udp -s  154.17.226.43 --dport 53 -j ACCEPT && iptables -I INPUT 1 -p tcp -s  154.17.226.43 --dport 53 -j ACCEPT
```
注意顺序，现执行的命令优先级越高，可通过`-I` 参数将新ip插到第一行，以此来提高优先级

删除规则：
```
iptables -D INPUT -p udp -s 154.17.226.43 --dport 53 -j ACCEPT && iptables -D INPUT -p tcp -s 154.17.226.43 --dport 53 -j ACCEPT && iptables -D INPUT -p udp --dport 53 -j DROP && iptables -D INPUT -p tcp --dport 53 -j DROP

```
https://chatgpt.com/share/670e8242-c550-8011-a226-03e87696c1ab

确保当前的 `iptables` 规则在系统重启后依然有效
```
apt -y install netfilter-persistent iptables-persistent && netfilter-persistent save
```
- `netfilter-persistent` 管理和保存当前的 `iptables` 规则。
- `iptables-persistent` 提供了保存和恢复 `iptables` 规则的机制，并与 `netfilter-persistent` 一起工作。
- 存当前的 `iptables` 和 `ip6tables` 规则，并将其分别保存到 `/etc/iptables/rules.v4`（IPv4 规则）和 `/etc/iptables/rules.v6`（IPv6 规则）
显示保存的 IPv4 `iptables` 规则
```
cat /etc/iptables/rules.v4
```


采用snell v4时 记得把dns地址设为127.0.0.1

sudo systemctl start dnsmasq
sudo systemctl enable dnsmasq
sudo systemctl status dnsmasq
sudo systemctl restart dnsmasq
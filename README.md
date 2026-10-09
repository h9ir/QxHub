[general]
server_check_url=http://www.gstatic.com/generate_204
server_check_timeout=5000
dns_exclusion_list=*.cmpassport.com, *.jegotrip.com.cn, *.icitymobile.mobi, id6.me
fallback_udp_policy=direct

[dns]
server=223.5.5.5
server=119.29.29.29
doh-server=https://1.1.1.1/dns-query

[policy]
static=手动选择, server-tag-regex=.*
url-latency-benchmark=自动选择, server-tag-regex=.*, check-interval=600, alive-checking=false
static=香港节点, server-tag-regex=(香港|Hong Kong)
static=日本节点, server-tag-regex=(日本|Japan)
static=新加坡节点, server-tag-regex=(新加坡|Singapore)
static=美国节点, server-tag-regex=(美国|United States)

[filter_remote]
FILTER_LAN, tag=局域网规则, force-policy=direct, enabled=true
FILTER_REGION, tag=地区规则, force-policy=direct, enabled=true

[filter_local]
# Apple 服务
host-suffix, apple.com, direct
host-suffix, icloud.com, direct
host-suffix, apple-cloudkit.com, direct
host-suffix, mzstatic.com, direct

# AI 服务
host-suffix, openai.com, 手动选择
host-suffix, chatgpt.com, 手动选择
host-suffix, oaistatic.com, 手动选择
host-suffix, oaiusercontent.com, 手动选择
host-suffix, claude.ai, 手动选择
host-suffix, anthropic.com, 手动选择
host-suffix, gemini.google.com, 手动选择

# Google 与 YouTube
host-suffix, google.com, 手动选择
host-suffix, googleapis.com, 手动选择
host-suffix, gstatic.com, 手动选择
host-suffix, youtube.com, 手动选择
host-suffix, googlevideo.com, 手动选择
host-suffix, ytimg.com, 手动选择

# 常见社交平台
host-suffix, x.com, 手动选择
host-suffix, twitter.com, 手动选择
host-suffix, tiktok.com, 手动选择
host-suffix, instagram.com, 手动选择
host-suffix, facebook.com, 手动选择
host-suffix, reddit.com, 手动选择

# 国内常用服务
host-suffix, bilibili.com, direct
host-suffix, bilivideo.com, direct
host-suffix, qq.com, direct
host-suffix, weixin.qq.com, direct
host-suffix, taobao.com, direct
host-suffix, alipay.com, direct
host-suffix, jd.com, direct
host-suffix, zhihu.com, direct

# 局域网地址
host-suffix, local, direct
ip-cidr, 10.0.0.0/8, direct
ip-cidr, 127.0.0.0/8, direct
ip-cidr, 169.254.0.0/16, direct
ip-cidr, 172.16.0.0/12, direct
ip-cidr, 192.168.0.0/16, direct
ip-cidr, 224.0.0.0/4, direct
ip6-cidr, fe80::/10, direct

# 国内 IP 直连
geoip, cn, direct

# 兜底规则
final, 手动选择

# 电脑端鸣潮国际服代理
将域名和UDP分开代理
## 使用方法一
```yaml
# 订阅规则
rule-providers:
  WutheringWaves:
    type: http
    behavior: classical
    format: yaml
    path: './rules/WutheringWaves.yaml'
    url: 'https://raw.githubusercontent.com/Heihuaf/Proxy-rule/refs/heads/main/Clash/WutheringWaves/WutheringWaves.yaml'
    interval: 3600

  WutheringWavesUDP:
    type: http
    behavior: classical
    format: yaml
    path: './rules/WutheringWavesUDP.yaml'
    url: 'https://raw.githubusercontent.com/Heihuaf/Proxy-rule/refs/heads/main/Clash/WutheringWaves/WuthetingWavesUDP.yaml'
    interval: 3600
    
# 规则指向
rules:
  # 鸣潮域名代理
  - RULE-SET,WutheringWaves,DIRECT
  # 鸣潮UDP代理
  - RULE-SET,WutheringWavesUDP,DIRECT
```


## 使用方法二，目前用的，抄的大佬的配置
```yaml
# 配置作者：https://t.me/iKeLee
# 适用版本：所有使用 mihomo 核心的程序
# 锚点 - 规则参数 [每小时更新一次订阅规则，更新规则时使用DIRECT]
RuleProviders: &RuleProviders {type: http, behavior: classical, interval: 3600, format: yaml, proxy: DIRECT}

# 订阅规则
rule-providers:
  WutheringWaves:
    <<: *RuleProviders
    path: './rules/WutheringWaves.yaml'
    url: 'https://raw.githubusercontent.com/Heihuaf/Proxy-rule/refs/heads/main/Clash/WutheringWaves/WutheringWaves.yaml'

  WutheringWavesUDP:
    <<: *RuleProviders
    path: './rules/WutheringWavesUDP.yaml'
    url: 'https://raw.githubusercontent.com/Heihuaf/Proxy-rule/refs/heads/main/Clash/WutheringWaves/WuthetingWavesUDP.yaml'

# 规则指向
rules:
  # 鸣潮域名代理
  - RULE-SET,WutheringWaves,DIRECT
  # 鸣潮UDP代理
  - RULE-SET,WutheringWavesUDP,DIRECT
```

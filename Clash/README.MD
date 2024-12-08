使用方法一
```
# 订阅规则
rule-providers:
  WutheringWaves:
    type: http
    behavior: classical
    format: yaml
    path: './rules/WutheringWaves.yaml'
    url: 'https://raw.githubusercontent.com/Heihuaf/Proxy-rule/refs/heads/main/Clash/WutheringWaves.yaml'
    interval: 3600
    
# 规则指向
rules:
  # 自行修改策略
  - RULE-SET, WutheringWaves, DIRECT 
```

使用方法二，目前用的，抄的大佬的配置
```
# 配置作者：https://t.me/iKeLee
# 适用版本：所有使用 mihomo 核心的程序
# 锚点 - 规则参数 [每小时更新一次订阅规则，更新规则时使用DIRECT]
RuleProviders: &RuleProviders {type: http, behavior: classical, interval: 3600, format: yaml, proxy: DIRECT}

# 订阅规则
rule-providers:
  WutheringWaves:
    <<: *RuleProviders
    path: './rules/WutheringWaves.yaml'
    url: 'https://raw.githubusercontent.com/Heihuaf/Proxy-rule/refs/heads/main/Clash/WutheringWaves.yaml'

# 规则指向
rules:
  # 自行修改策略
  - RULE-SET, WutheringWaves, DIRECT
```

# 电脑端鸣潮国际服代理
将域名和UDP分开代理
## 使用方法
```yaml
# 锚点 - 规则参数 [每12小时更新一次订阅规则，更新规则时使用🌐全球策略]
RuleSet_classical: &RuleSet_classical {type: http, behavior: classical, interval: 43200, format: yaml, proxy: 🌐全球}
RuleSet_domain: &RuleSet_domain {type: http, behavior: domain, interval: 43200, format: yaml, proxy: 🌐全球}
RuleSet_ipcidr: &RuleSet_ipcidr {type: http, behavior: ipcidr, interval: 43200, format: yaml, proxy: 🌐全球}

# 订阅规则
rule-providers:
  WutheringWaves:
    <<: *RuleSet_domain
    path: './rules/WutheringWaves.yaml'
    url: 'https://raw.githubusercontent.com/Heihuaf/Proxy-rule/refs/heads/main/Clash/WutheringWaves/WutheringWaves.yaml'

  WutheringWavesUDP:
    <<: *RuleSet_ipcidr
    path: './rules/WutheringWavesUDP.yaml'
    url: 'https://raw.githubusercontent.com/Heihuaf/Proxy-rule/refs/heads/main/Clash/WutheringWaves/WuthetingWavesUDP.yaml'

# 规则指向
rules:
  # 鸣潮域名代理
  - RULE-SET,WutheringWaves,DIRECT
  # 鸣潮UDP代理
  - RULE-SET,WutheringWavesUDP,DIRECT
```

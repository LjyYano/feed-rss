# feed-rss

微信公众号、Twitter 等 RSS 源。

## 微信公众号 RSS

`wechat_feeds.txt` 中每行配置一个 RSS 源：

```text
slug,source_url
```

`source_url` 支持两种形式：

- 公开可访问的 RSS/Atom 地址
- `rsshub-local:/route`：GitHub Actions 临时启动本地 RSSHub 并抓取对应路由

例如：

```text
shinsi,https://wechat2rss.bestblogs.dev/feed/3e6fcb56a39b2e18f1036113655d4ff8fe726b62.xml
youyouluming,https://wechat2rss.xlab.app/feed/fa89f27259f903b92f5f133140dd3f641110f9fd.xml
zhangbeihai,rsshub-local:/wechat/sogou/zengyuanweilai
```

GitHub Actions 每天拉取一次源内容，校验为有效 RSS/Atom 后保存到 `docs/feeds/`，再通过 GitHub Pages 提供稳定订阅地址。

最终订阅地址格式：

```text
https://ljyyano.github.io/feed-rss/feeds/{slug}.xml
```

批量订阅可使用：

```text
https://ljyyano.github.io/feed-rss/wechat.opml
```

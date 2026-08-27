# feed-rss

微信公众号、Twitter 等 RSS 源。

## 微信公众号 RSS

`wechat_feeds.txt` 中每行配置一个公开 RSS/Atom 源：

```text
slug,source_url
```

GitHub Actions 每天拉取一次源内容，校验为有效 RSS/Atom 后保存到 `docs/feeds/`，再通过 GitHub Pages 提供稳定订阅地址。

例如：

```text
shensi,https://wechat2rss.bestblogs.dev/feed/3e6fcb56a39b2e18f1036113655d4ff8fe726b62.xml
```

最终订阅地址：

```text
https://ljyyano.github.io/feed-rss/feeds/shensi.xml
```

批量订阅可使用：

```text
https://ljyyano.github.io/feed-rss/wechat.opml
```

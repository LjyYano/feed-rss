# feed-rss

微信公众号、Twitter 等 RSS 源。

## 微信公众号 RSS

`wechat_feeds.txt` 每行格式：

```text
slug,source_url,author_filter
```

- `source_url`：公开 RSS/Atom 地址，或 `rsshub-local:/route`
- `author_filter`：可选；设置后只保留 `<author>` 精确匹配的文章，适合过滤 RSSHub 搜狗搜索中的无关结果

例如：

```text
shensi,https://wechat2rss.bestblogs.dev/feed/3e6fcb56a39b2e18f1036113655d4ff8fe726b62.xml
youyouluming,https://wechat2rss.xlab.app/feed/fa89f27259f903b92f5f133140dd3f641110f9fd.xml
zhangbeihai,rsshub-local:/wechat/sogou/zengyuanweilai,章北海的自然选择
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

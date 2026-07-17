# 💬 NBA Talk — a serverless NBA discussion forum

**Live site:** https://yaoyugua.github.io/day_10/

A discussion-channel forum ("Where will LeBron go?", "Trade deadline talk", …)
in a single static `index.html` — no server, no database, no build step.
Powered by [giscus](https://giscus.app): every channel is a thread in this
repo's [GitHub Discussions](https://github.com/yaoyugua/day_10/discussions),
and visitors sign in with GitHub to post.

## Features

- 📺 **Channels** — sidebar of discussion topics; each maps to one GitHub Discussion
- ➕ **Create channel** — anyone can start a topic; the thread is created on
  GitHub when the first comment is posted
- 🔗 **Shareable links** — `?channel=Where%20will%20LeBron%20go%3F` deep-links a channel
- 🌙 Dark, GitHub-flavored UI, hosted free on GitHub Pages

## How it works

`index.html` embeds the giscus widget with `data-mapping="specific"`, using the
channel name as the discussion term — so each channel gets its own thread.
Posts live in GitHub Discussions (category: *General*), which means moderation,
reactions, and notifications all come free from GitHub.

## Local development

giscus won't load from a `file://` page, so serve the folder:

```bash
python3 -m http.server 8765
# then open http://localhost:8765/
```

# comics/

Published comic output for the [process.ink](https://process.ink) website.

Each approved run commits 5 files:

```
comics/
  {run_id}.svg              # Winner (horizontal)
  {run_id}-vertical.svg     # Winner (vertical, mobile)
  {run_id}-a.svg            # Variant A
  {run_id}-b.svg            # Variant B
  {run_id}.json             # Public metadata (website data contract)
```

## {run_id}.json Schema

```jsonc
{
  "run_id": "v0.0.1",
  "date": "2026-02-06",
  "timestamp": "2026-02-06T12:00:00+00:00",
  "topic": "remote work fatigue",
  "topic_source": "news",
  "style_snapshot": {
    "line_weight": "medium",
    "palette": "muted_earth",
    "accent_color": "#E63946",
    "panel_count": 3,
    "humor_style": "deadpan",
    "detail_level": "minimal",
    "character_style": "geometric_simple"
  },
  "characters": ["Cache", "Sifaka"],
  "learned": "Deadpan delivery lets the philosophical weight land harder",
  "explore": {
    "dimension": "humor_style",
    "variant_a_value": "deadpan",
    "variant_b_value": "absurdist"
  },
  "winner": {
    "variant": "A",
    "file": "v0.0.1.svg"
  },
  "variants": {
    "a": "v0.0.1-a.svg",
    "b": "v0.0.1-b.svg"
  },
  "posting": {
    "ab_tweet_id": "1234567890",
    "ab_post_url": "https://x.com/i/status/1234567890",
    "winner_tweet_id": "1234567891",
    "winner_post_url": "https://x.com/i/status/1234567891"
  },
  "voting": {
    "collected_at": "2026-02-06T15:00:00+00:00",
    "total_replies": 25,
    "parsed_votes": 18,
    "a_votes": 12,
    "b_votes": 6,
    "winner": "A",
    "margin": 0.67
  }
}
```

## How It Works

When a comic is approved via the publishing platform's `/approve` endpoint, `commit_to_comic_repo()` clones this repo, writes the 5 files to `comics/`, commits, and pushes. The `notify-website.yml` workflow then triggers a rebuild of the process.ink website.

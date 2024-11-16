# Kite - News. Elevated.

This repository contains public files for [Kite](https://kite.kagi.com), news app for people who want a healthy news diet, developed by [Kagi](https://kagi.com).

Kite is  designed for people who want to stay informed without getting overwhelmed. We provide thrice-daily updates of the most important news stories, from carefully curated sources and summarized by advanced language models to give you the essential information you need.

Most of what powers Kite is open sourced and is found in this repository.

This includes
- Kite web app
- Community curated feeds
- Media information
  
## Core Principles

- Updated only three times per day - no endless scrolling
- Facts and perspectives, opinion-free
- Zero tracking, zero ads
- Pure signal, no noise
- Quality over quantity
- Complete news diet in 5 minutes

You can read more about core principles behind Kite 
- [Avoid News: Towards a Healthy News Diet](https://www.gwern.net/docs/culture/2010-dobelli.pdf) ([HN discussion](https://news.ycombinator.com/item?id=21430337))
- [News is bad for you](http://www.theguardian.com/media/2013/apr/12/news-is-bad-rolf-dobelli) ([HN discussion](https://news.ycombinator.com/item?id=6894244))
- [Stop reading news](https://fs.blog/2013/12/stop-reading-news/) ([HN discussion](https://news.ycombinator.com/item?id=19084099))

If you prefer to watch a short video, check this Ted talk:  [Four reasons you should stop watching the news | Rolf Dobelli](https://www.youtube.com/watch?v=-miTTiaqFlI).

# Install & run Kite front-end

Kite front end is a statically served app and is fully open source.

Here is how to run it locally.

```
pip install Jinja2
python generate.py
open index.html
```

Kite front-end uses Kite application data that can be found starting at [kite.kagi.com/kite.json](https://kite.kagi.com/kite.json), then explore from there. Note that kite.json and files referenced by it are licensed under [CC BY-NC license](https://creativecommons.org/licenses/by-nc/4.0/). This means that this data can be used free of charge (with attribution and for non-commercial use). If you would like to license this data for commercial use let us know through support@kagi.com.

Kite web app is just one example front-end that one can run on top of the Kite data. We encourage others to contribute improvements to the Kite frontend.

**We would also love to see what kind of custom front-ends you can create on top of Kite data!** Feel free to share them with us and others by editing this Readme file.

## Editing categories

To edit community curated categories, submit a pull request editing `kite_feeds.json`. If you do not know how to do that, you can [open an issue](https://github.com/kagisearch/kite-public/issues/new/choose) and share the feeds you want to add there.

This file contains RSS feeds for various categories.

To add a new category or modify existing ones, follow this structure:

```jsonc
{
  "Category Name": {
    "feeds": [
      "https://example.com/rss-feed-1",
      "https://example.com/rss-feed-2"
      // ...
    ]
  },
  "Another Category": {
    "feeds": [
      "https://another-example.com/rss-feed-1",
      "https://another-example.com/rss-feed-2"
      // ...
    ]
  }
}
```

### Adding a new category

1. Create a new object with the category name as the key
2. Add a "feeds" array containing the RSS feed URLs for that category
3. Ensure proper JSON formatting (commas between objects, no trailing comma)

All categories are created equal and will appear as top level categories in the Kite app.

Ideas for categories:

- Local news (city/state level)
- Regional news (country/region)
- Topical news (health, machine learning, aviation ...)


### Guidelines for adding RSS feeds

Kite does not scrape websites, but only publicly available RSS feeds.

When adding an RSS feed make sure to:

- Check that feed is working and has recent (daily) content.
- Choose sources that have high quality content. Do not use low quality/gossip/SEO content.
- Feeds should be in the same language as the rest of the feeds in that category (do not mix languages)

### Important

We require at least **25 feeds** for a category in order to surface it in Kite news. This is to make sure we maintain high level of quality of events covered in the app. The more high quality feeds exist for a category, the better Kite coverage will be. The feeds should be using the same language.

Kite does not scrape news websites, it only uses publicly available information in RSS feeds.

## Guideline for editing Media information

Kite uses contents of `media_data.json` to show additional information about sources of information. Initial information has been sources from https://statemediamonitor.com/ and the classification methodology  is explained here https://statemediamonitor.com/methodology/

Feel free to add additional information (by editing `media_data.json`) both for privatly owned and state funded media organization. Add your sources of information in the pull request.

---
layout: post
title:  Building a markdown-based blog with Jekyll and github pages
date:   2019-10-30
# updated: 2019-01-02b
tags:
- jekyll
- markdown
---

* be sure to cache correctly! I ended up doing <a href="https://docs.travis-ci.com/user/caching#cache-rvm-ruby-version-for-non-ruby-projects" target="_blank">this</a>:
  ```yaml
  cache:
    directories:
      - /home/travis/.rvm/
  ```
  It reduced my build times from about 3 minutes 20 seconds to about 45 seconds.
    
  ![screenshot showing two markedly different build times; 3 minutes and 28 seconds before this change, versus 46 seconds after.](/blog/images/faster-builds.png)

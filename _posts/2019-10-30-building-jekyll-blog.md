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
  It reduced my total build times from an average of 3 minutes 20 seconds to an average of 45 seconds, or about four times faster.
    
  ![screenshot showing two markedly different build times; 3 minutes and 28 seconds before this change, versus 46 seconds after.](/blog/images/faster-builds.png)
  
  The <a href="https://travis-ci.org/chadlavi/blog/builds/605132241" target="_blank">last  build before the change</a> had an install time of 153.21 seconds; the <a href="https://travis-ci.org/chadlavi/blog/builds/605134945" target="_blank">first build after the change</a> had a build time of _0.38 seconds_. That's roughly 400 times faster.
  
  You can see the full build log for this blog at <a href="https://travis-ci.org/chadlavi/blog/builds" target=_blank">https://travis-ci.org/chadlavi/blog/builds</a>

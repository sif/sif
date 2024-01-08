---
layout: post
title: "Beautiful Soup and Scraping"
categories: python
tags: beautiful_soup web_scraping python html_parser bs4 crawler
---

I have updated this post. You could use this boilerplate code to get started. I got it from Wikipedia and replace mine with it because it's so much cleaner. 

```
#!/usr/bin/env python3
# Anchor extraction from HTML document
from bs4 import BeautifulSoup
from urllib.request import urlopen
with urlopen('https://en.wikipedia.org/wiki/Main_Page') as response:
    soup = BeautifulSoup(response, 'html.parser')
    for anchor in soup.find_all('a'):
        print(anchor.get('href', '/'))
```

Of course, you will need to modify this. I created a small crawler to go and download pictures of chihuahuas.

There ~~are~~ was some legal issues with scraping but as long as it's done in good faith, it should be okay. 

<img src="https://github.com/sif/sif/raw/main/pictures/chihuahua.png" />

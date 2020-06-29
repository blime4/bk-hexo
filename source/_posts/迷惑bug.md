---
title: '[迷惑bug]'
tags:
  - bug
categories: chaos
hide: true
abbrlink: b782c81a
date: 2020-06-29 15:36:05
---

迷惑BUG1

`有bug`
```
from selenium import webdriver

options = webdriver.ChromeOptions()
options.add_argument('–no-sandbox')
options.add_argument('–headless')
options.add_argument('--disable-dev-shm-usage')
driver = webdriver.Chrome(chrome_options=options)
driver.get("https://www.baidu.com")
print(driver.page_source)
driver.quit()
```

`无bug`
```
from selenium.webdriver.chrome.options import Options
chrome_options = Options()
chrome_options.add_argument('--no-sandbox')
chrome_options.add_argument('--disable-dev-shm-usage')
chrome_options.add_argument('--headless')
browser = webdriver.Chrome(chrome_options=chrome_options)
browser.get("https://www.baidu.com")
print(browser.page_source)
browser.quit()
```
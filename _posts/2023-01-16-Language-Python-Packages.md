---
layout: post
title:  "파이썬(Python) - 패키지 종속성 관리"
crawlertitle: "About Python Packages"
summary: "Python"
date:   2023-01-16 18:00:00 +0900
categories: posts
tags: ['Language']
author: Yeonghyeon Kim
---

라이브러리를 사용하여 개발한 프로그램이라면 다른 PC에서 사용할때 동일한 버전의 라이브러리 사용이 권장됩니다.<br><br>
사용하고 있는 라이브러리 종속성 정보를 추출하고 복원하는 방법을 알아봅니다.

__추출__

``` bash
pip freeze > requirements.txt
```

__복원__

```bash
pip install -r requirements.txt
```

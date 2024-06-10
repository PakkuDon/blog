---
# post-bundle archtype taken from https://stackoverflow.com/a/69690870
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
description: One-line summary. Used in index page and meta tags
draft: true
tags:
  - example
  - tag
---


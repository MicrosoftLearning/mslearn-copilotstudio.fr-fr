---
title: Instructions hébergées en ligne
permalink: index.html
layout: home
---

# Exercices Copilot Studio

Les liens vers les exercices Copilot Studio sur Microsoft Learn sont répertoriés ci-dessous.

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %} {% for activity in labs  %}
- [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) {% endfor %}

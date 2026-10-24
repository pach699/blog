---
layout: default
title: 关于我
permalink: /about.html
---

<section class="wrap section about" aria-labelledby="about-title">
  <div><p class="eyebrow">A little about me</p><h1 id="about-title">关于我</h1><div class="rule"></div></div>
  <div class="about-note">
    <p>{{ site.author.bio }}</p>
    <p>现在主要在做两件事：把学到的东西写成别人能看懂的文字，把想法做成能打开链接的作品。这个博客就是其中一件。</p>
    <ul class="tag-list"><li>网页</li><li>写作</li><li>设计</li><li>学习中</li></ul>
  </div>
</section>

<section class="wrap section about" aria-labelledby="contact-title">
  <div><p class="eyebrow">Get in touch</p><h2 id="contact-title">联系我</h2><div class="rule"></div></div>
  <div class="about-note">
    <p>想聊点什么，或者发现文章里有写错的地方，都可以直接找我。</p>
    <ul class="contact-list">
      <li><span>邮箱</span><a href="mailto:{{ site.author.email }}">{{ site.author.email }}</a></li>
      <li><span>GitHub</span><a href="{{ site.author.github }}">{{ site.author.github | remove: 'https://' }}</a></li>
    </ul>
  </div>
</section>

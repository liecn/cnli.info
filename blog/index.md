---
layout: home
permalink: /event-horizon/
---

<div class="index-content col6">
    <div class="section">
        <ul class="artical-cate">
            <li class="on"><a href="/event-horizon"><span>Bang</span></a></li>
            <li><a href="{{ site.dir_main }}/gadgets"><span>发明家</span></a></li>
            <li><a href="{{ site.dir_main }}/chatterbox"><span>话匣子</span></a></li>
            <li><a href="{{ site.dir_main }}/review"><span>观后感</span></a></li>
            <li><a href="{{ site.dir_main }}/collections"><span>广囤粮</span></a></li>
            <li><a href="{{ site.dir_main }}/archive"><span>水逆</span></a></li>
        </ul>
        <div class="cate-bar"><span id="cateBar"></span></div>
        <ul class="artical-list">
        <br>
        <h4>这里是<a href="https://zh.wikipedia.org/wiki/%E4%BA%8B%E4%BB%B6%E8%A6%96%E7%95%8C">事件视界</a>，外面的观察者无法观察到其内部，通常可以通过站内的虫洞到达。</h4>
        <br>
        {% for post in site.categories.blog %}
            <hr>
            <li>
                <h2>
                    <a href="{{ post.url }}">{{ post.title }}</a>
                </h2>
                <div class="title-desc">{{ post.description }}</div>
            </li>
        {% endfor %}
        </ul>
    </div>
    <div class="aside">
    </div>
</div>

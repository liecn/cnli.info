---
layout: home
permalink: /event-horizon/
---

<div class="index-content col6">
    <div class="section">
        <ul class="artical-cate">
            <li class="on"><a href="/event-horizon"><span>Bang</span></a></li>
            <li><a href="/gadgets"><span>捣点东西</span></a></li>
            <li><a href="/photographs"><span>拍点照片</span></a></li>
            <li><a href="/sports"><span>做点运动</span></a></li>
            <li><a href="/collections"><span>攒点收藏</span></a></li>
            <li><a href="/archive"><span>回到过去</span></a></li>
        </ul>
        

        <div class="cate-bar"><span id="cateBar"></span></div>

        <ul class="artical-list">
        <br>
        <h4>这里是<a href="https://zh.wikipedia.org/wiki/%E4%BA%8B%E4%BB%B6%E8%A6%96%E7%95%8C">事件视界</a>，外面的观察者无法观察到其内部，通常可以通过站内的虫洞到达。</h4>
        <br>
        {% for post in site.categories.gaia %}
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

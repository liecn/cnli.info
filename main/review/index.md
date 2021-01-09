---
layout: home
---

<div class="index-content col4">
    <div class="section">
        <ul class="artical-cate">
            <li><a href="/"><span>Gaia</span></a></li>
            <li><a href="{{ site.dir_main }}/gadgets"><span>发明家</span></a></li>
            <li><a href="{{ site.dir_main }}/chatterbox"><span>话匣子</span></a></li>
            <li class="on"><a href="{{ site.dir_main }}/review"><span>观后感</span></a></li>
            <li><a href="{{ site.dir_main }}/collections"><span>广囤粮</span></a></li>
            <li><a href="{{ site.dir_main }}/archive"><span>水逆</span></a></li>
        </ul>
        <div class="cate-bar"><span id="cateBar"></span></div>
        <ul class="artical-list">
        {% for post in site.categories.review %}
            <hr>
            <li>
                <h2 class="post-title">
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

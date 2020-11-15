---
layout: home
---

<div class="index-content col3">
    <div class="section">
        <ul class="artical-cate">
            <li><a href="/"><span>Gaia</span></a></li>
            <li><a href="/gadgets"><span>捣点东西</span></a></li>
            <li class="on"><a href="/photographs"><span>拍点照片</span></a></li>
            <li><a href="/sports"><span>做点运动</span></a></li>
            <li><a href="/archive"><span>回到过去</span></a></li>
        </ul>
        <div class="cate-bar"><span id="cateBar"></span></div>
        <ul class="artical-list">
        {% for post in site.categories.viewfinder %}
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

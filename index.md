---
layout: home
---

<div class="index-content blog">
    <div class="section">
        <ul class="artical-cate">
            <li class="on"><a href="/"><span>Blog</span></a></li>
            <li style="text-align:center"><a href="/Notes"><span>Notes</span></a></li>
            <li style="text-align:right"><a href="/Stories"><span>Stories</span></a></li>
        </ul>

        <div class="cate-bar"><span id="cateBar"></span></div>

        <ul class="artical-list">
        {% for post in site.categories.blog %}
            <li>
                <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
                <div class="title-desc">{{ post.description }}</div>
            </li>
        {% endfor %}
        </ul>
    </div>
    <div class="aside">
    </div>
    
    <ul class="pagination">
        <li>
            <a href="{{ site.baseurl}}/article/">
                <span>首页</span>
            </a>
        </li>
        <li>
        {% if paginator.page == 1 %}
            <span>&laquo;</span>
        {% else %}
            {% if paginator.previous_page == 1 %}
            <a href="{{ site.baseurl}}/article/">
            {% else %}
            <a href="{{ site.baseurl}}/article/{{ paginator.previous_page }}">
            {% endif %}
                <span>&laquo;</span>
            </a>
        {% endif %}
        </li>
        {% for i in (1..paginator.total_pages) limit:5 offset:{{paginator.page-1}} %}
            {% if paginator.page == i %}
        <li class="active">
            {% else %}
        <li>
            {% endif %}
            {% if i == 1 %}
            <a href="{{site.baseurl}}/article">{{i}}</a>
            {% else %}
            <a href="{{site.baseurl}}/article/{{i}}">{{i}}</a>
            {% endif %}
        </li>
        {% endfor %}
        <li>
            {% if paginator.page == paginator.total_pages %}
            <span>&raquo;</span>
            {% else %}
            <a href="{{ site.baseurl}}/article/{{ paginator.next_page }}">
                <span>&raquo;</span>
            </a>
            {% endif %}
        </li>
        <li>
            <a href="{{ site.baseurl}}/article/{{paginator.total_pages}}">
                <span>末页</span>
            </a>
        </li>
        <li class="disabled">
            <span>第{{paginator.page}}页 / 共{{paginator.total_pages}}页</span>
        </li>
</ul>

</div>



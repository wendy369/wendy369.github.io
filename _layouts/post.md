---
layout: default
---
<script type="text/javascript">
	$(function () {
		$('#nav1').addClass('active');
	});
</script>
<div class="page-top-nav clearfix">
	<div class="categoryList">
		<strong>分类：</strong>
		{% for category in page.categories %}
	        <a href="http://wendy369.github.io/categories/#{{ category }}" itemprop="url">{{ category }}</a> 
	    {% endfor %}<br />
	    <strong>标签：</strong>
	    {% for tag in page.tags limit:3 %}
	        <a href="http://wendy369.github.io/tags/#{{ tag }}" itemprop="url">{{ tag }}</a> 
	    {% endfor %}
	</div>
	<div class="page-paginator">
		<span title="{{page.previous.title}}">
		{% if page.previous.url %} 
			上一篇：<a href="{{page.previous.url}}">{{page.previous.title}}</a>
	    {% endif %}
		</span><br />
		<span title="{{page.next.title}}">
	        {% if page.next.url %} 
			下一篇：<a href="{{page.next.url}}">{{page.next.title}}</a>
	        {% endif %} 
		</span>
	</div>
</div>
<div class="container content">
	<h3 class="post-title">{{ page.title }}</h3>
	<div class="post-title-line"></div>
	<div class="post-content">
	{{ content }}
	</div>
	<div class="post-time-line">
		分类：<span class="post-time-line-categories">{{ page.categories }}</span>&nbsp;&nbsp;|&nbsp;&nbsp;
		标签：
		{% for tag in page.tags %}
			<span class="post-time-line-tag">{{ tag }}</span>
		{% endfor %}
		&nbsp;&nbsp;|&nbsp;&nbsp;
		<time datetime="{{ page.date | date:"%Y-%m-%d" }}">{{ page.date | date:"%Y-%m-%d" }}</time>
	</div>
	
	{% include disqus.snippet %}

	{% include comments.md %}
</div>
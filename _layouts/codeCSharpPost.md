<!DOCTYPE html>
<html>
  <head>
    <meta http-equiv="content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>{{ page.title }}</title>
    <link rel="fluid-icon" href="/fluidicon.png" />
    <link rel="apple-touch-icon" sizes="57x57" href="/images/apple-touch-icon-114.png" />
    <link rel="apple-touch-icon" sizes="114x114" href="/images/apple-touch-icon-114.png" />
    <link rel="apple-touch-icon" sizes="72x72" href="/images/apple-touch-icon-144.png" />
    <link rel="apple-touch-icon" sizes="144x144" href="/images/apple-touch-icon-144.png" />
    <link rel="icon" type="image/x-icon" href="/images/favicon.ico" />
    <link rel="stylesheet" href="/bootstrap-3.0.3/css/bootstrap.min.css" />
    <link rel="stylesheet" href="/css/style.css" />
    <script src="/js/jquery-2.1.1.min.js"></script>
    <script src="/bootstrap-3.0.3/js/bootstrap.min.js"></script>
  	<script type="text/javascript" src="/syntaxhighlighter_3.0.83/scripts/shCore.js"></script>
  	<script type="text/javascript" src="/syntaxhighlighter_3.0.83/scripts/shBrushCSharp.js"></script>
  	<link type="text/css" rel="stylesheet" href="/syntaxhighlighter_3.0.83/styles/shCoreDefault.css"/>
    <script type="text/javascript">
  		$(function () {
  			$('#nav1').addClass('active');
  		});
  		SyntaxHighlighter.all();
  		SyntaxHighlighter.defaults['toolbar'] = false;
  	</script>
    <script type="text/javascript">
        $(function () {
            $(window).scroll(function () {
                var scrolltop = $(this).scrollTop();
                if (scrolltop >= 100) {
                    $("#elevator_item").show();
                } else {
                    $("#elevator_item").hide();
                }
            });
            $("#elevator").click(function () {
                $("html,body").animate({ scrollTop: 0 }, 500);
            });
            $(".qr").hover(function () {
                $(".qr-popup").show();
            }, function () {
                $(".qr-popup").hide();
            });
        });
    </script>
  </head>
  <body>
    <div>
      {% include navigation.md %}
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
			{% include comments.md %}
		</div>
    <div class="container footer">
      {% include footer.md %}
    </div>
  </body>
</html>
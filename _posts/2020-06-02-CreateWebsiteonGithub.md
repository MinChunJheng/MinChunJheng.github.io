---
layout: post
title: 在github上建立個人網站
date: 2020-06-02
tags: blog
---

在github上建立個人網站，由於自己第一次想要建立個人網站，遇到許多瓶頸，因此想要紀錄下來，在github上建立個人網站需要使用到:  
html, github, jekyll, markdown.  
網路上的步驟雖然方便安裝但對於接下來的控管，對新人來說是一大負擔，我會想要一步一步建立github page.

開始創建一個github page:
---

1.在[Github](https://github.com/)中創建自己的帳號，並且創建名為`username.github.io`的repository。

2.在repository主目錄下建立名為`index.html`的新檔案，填入以下內容。

{% highlight liquid %}        

    <!DOCTYPE html>
    <html>
	  <head>
		    <title>First</title>
	  </head>
	  <body>
		<nav>
    		<ul>
        		<li><a href="/">Home</a></li>
	        	<li><a href="/about">About</a></li>
        		<li><a href="/blog">Blog</a></li>
    		</ul>
		</nav>
		<div class="container">
    		<div class="blurb">
        		<h1>heading</h1>
				<p>Text</a></p>
    		</div><!-- /.blurb -->
		</div><!-- /.container -->
		<footer>
    		<ul>
        		<li><a href="url">link1</a></li>
        		<li><a href="url">lnik2</a></li>
			</ul>
		</footer>
    </body>
    </html>        
{% endhighlight %}

3.在repository主目錄下建立名為`css/main.css`的新檔案，用以調整面板，例如:

{% highlight liquid %}

    body {
    margin: 60px auto;
    width: 70%;
    }
    nav ul, footer ul {
        font-family:'Helvetica', 'Arial', 'Sans-Serif';
        padding: 0px;
        list-style: none;
        font-weight: bold;
    }
    nav ul li, footer ul li {
        display: inline;
        margin-right: 20px;
    }
    a {
        text-decoration: none;
        color: #999;
    }
    a:hover {
        text-decoration: underline;
    }
    h1 {
        font-size: 3em;
        font-family:'Helvetica', 'Arial', 'Sans-Serif';
    }
    p {
        font-size: 1.5em;
        line-height: 1.4em;
        color: #333;
   }

{% endhighlight %}

4.`index.html`連結`main.css`，在`index.html`的`<head>`間加入:

{% highlight liquid %}

    <!-- link to main stylesheet -->
    <link rel="stylesheet" type="text/css" href="/css/main.css">
    
{% endhighlight %}

至此您已經有blog的基礎樣板

Jekyll結構:
---

5.在repository主目錄下建立`.gitignore`檔案，讓github在建網頁時忽略特定檔案及資料夾      

{% highlight liquid %}

    site/

{% endhighlight %}

6.主目錄下建立`_config.yml`檔案，讓Jekyll知道專案的基礎信息。

{% highlight liquid %}

    name: username
    markdown: kramdown

{% endhighlight %}

7.建立`_layouts`資料夾，並在底下建立`default.html`。

{% highlight liquid %}

    <!DOCTYPE html>
    <html>
    <head>
      <title> page.title </title>
      <!-- link to main stylesheet -->
      <link rel="stylesheet" type="text/css" href="/css/main.css">
    </head>
    <body>
    <nav>
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/about">About</a></li>
            <li><a href="/blog">Blog</a></li>
        </ul>
    </nav>
    <div class="container">
         content
    </div><!-- /.container -->
    <footer>
        <ul>
            <li><a href="url">link1</a></li>
            <li><a href="url">lnik2</a></li>
      </ul>
    </footer>
    </body>
    </html>

{% endhighlight %}

8.更新主目錄的`index.html`:

{% highlight liquid %}

    layout: default
    title: MyBlog

{% endhighlight %}

開始第一篇文章
---

9.`_layouts`中創建`post.html`:

{% highlight liquid %}

    ---
    layout: default
    ---

    <h1> page.title </h1>
    <p class="meta">{{ page.date | date_to_string }}</p>

    <div class="post">
       content
    </div>

{% endhighlight %}

10.主目錄下建立`_posts`資料夾，並在底下建立新文件以`YYYY-MM-DD-title-of-my-post.md`命名

{% highlight liquid %}

    ---
    layout: post
    title: First Create Git Page
    date: 2020-06-01
    ---
    First Page

{% endhighlight %}

11. 主目錄下建立`blog`資料夾，並在底下建立`index.html`:

{% highlight liquid %}

    ---
    layout: default
    title: MyBlog
    ---
    <h1> page.title </h1>
    <ul class="posts">


{% endhighlight %}

至此已經主架構

code不完整，liquid content會影想到排版，先去掉

接下來就再慢慢研究，可以加入新功能:像是加入tag、留言板...等等

文章主要參考http://jmcglone.com/guides/github-pages/

---
layout: post
title:  "My incredible exam assignment!"

---
## CSS Preprocessors
CSS has been a staple in the world of web development. But it’s easy to get yourself tangled up in a mess once your project grows in size. For example, what if you’ve styled your website according to a specific style? Let’s say your client’s brand colors are supposed to be red and blue. So you’ve got elements styled with these as accent colors:

```
h1 {
	color: red;
}

.text-box {
	background-colors: red;
}
.article a:hover {
	color: yellow;
}
(Etc. etc. for dozens of other elements)
```

But then your client tells you their graphic designer suddenly decided to completely revamp their branding. Now their brand colors are green and purple, a perfectly wonderful color scheme, and they want the website to be congruent with that.

In regular CSS, this would be a pain. You’d have to manually change the colors for the dozens of classes, IDs and elements that needs change. What if there was an easier way, a smarter way, to get around this?

There is, and it’s called CSS preprocessing!

A CSS preprocessor is a program that has its own syntax. It’s not CSS, even though the syntax often appears very similar on the surface. The fact that each CSS preprocessor has its own “programming language” means that you’re able to be much more programmatic in your methodology. For example, you can include variables, perform simple arithmetic and so forth. For example, you can do this:

```
$primary-color: #33333;

body {
	background: $primary-color;
}
.card {
	background: $primary-color
}
```

Let’s say you need to change the primary color. Instead of having to go through all of your code, you can simply change the value of the $primary-color variable and get it over with immediately. This has the ability to save you much time and headache.

Not only does CSS preprocessors often allow for variables. I tried a CSS preprocessor called Sass, and it also allows you to use import in your code. You can import other pieces of external Sass code into your Sass-file. This enables you to split your styling up in modules, making your project easier to read and maintain.
After you’ve written the Sass code, you need to compile it. That is, translate the code into CSS so that it can actually affect the style of your web page. It’s done simply by writing 

```
sass yourSassFile.scss yourDesiredCssFilename.css
```

… in your terminal.

When I tried out Sass (or it’s most recent reincarnation Sassy CSS) I made use out of two of its features: Variables and includes. I really liked this because it made the code appear cleaner than with CSS. The only downside I saw was that it required some extra downtime to learn how to use the preprocessor, but that applies to every new technology, and the time you save in the long run can probably make it worthwhile anyway.

## Static site generators
I also used a static site generator called Jekyll, which allowed me to to generate a whole website using templates and only use markdown for the contents of each individual page. I didn’t have to hardcode each individual page in HTML.

I haven’t used a static site generator before. However, I have used the Python framework called Django, which utilizes a template language which has a syntax identical to that of Jekyll’s Liquid language. That enabled me to quickly get in the groove of things when it came to structuring the page templates, and I find the syntax quite easy to use, so that is a plus.

Other than that, I don’t have too much of an opinion on the subject. I’d probably prefer a framework in Javascript or Python for a larger project. But a static site generator like Jekyll might be suitable when you just want to get a small blog or site up and running, or create an MVP.

## Robot.txt
Services such as Google use programs called “crawlers” that comb through the web trying to find new web pages and information.  In the case of Google, they then use that data to index websites in their search engine.

Robots.txt is a document you can put on your server. It serves as an instruction to these bots and tells them which pages they’re allowed to visit and which not to, as well as if the pages should be indexed in search engines. 

Here’s how the robots.txt for my site:

```
User-agent: *
Disallow: /
```

I’ve simply disallowed all robots from crawling any of my pages.

The robot can ignore these instructions. For example, Google completely ignores the NoIndex rule of robots.txt since September 1st 2019. https://www.searchenginejournal.com/google-robots-txt-noindex/314961/ 

(They still adhere to robots.txt’s Disallow, albeit it doesn’t completely prevent your page from being indexed in Google) https://webmasters.googleblog.com/2019/07/a-note-on-unsupported-rules-in-robotstxt.html

## Humans.txt
I find humans.txt to be quite pointless. It’s  simply a text file to acknowledge the authors of a site. But here’s how I set it up:
```             
/* TEAM */            
Your title: Jon Mester       
Location: Sweden.

/* SITE */                     
Standards: HTML5, CSS3
Software: Jekyll, Ruby, Sass
```


## Other
I also implemented a comment section using Disqus on each of my blog posts. The process was simple. I signed up with Disqus, registered a website and name, and received an embed code  consisting of HTML and JS to put wherever I wished. 
       
                            
Another thing I used was Open Graph. It’s a protocol for giving other apps important data about your site, which allows them to include it whenever someone links to one of your pages, for example. You can include your page title, content, a “featured image”, canonical URL, author information and much more. 

You include this metadata on your page like this:

```
<meta property="og:title" content="My great blog post" />
<meta property="og:site_name" content="The world’s greatest blog" />
```

I made use of it as such:
```
<meta property="og:type" content="article">
<meta property="og:title" content="{{ page.title }}">
<meta property="og:url" content="{{ content.excerpt }}">
<meta property="article:author" content="Jon Mester">’

```

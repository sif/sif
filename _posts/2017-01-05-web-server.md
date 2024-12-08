---
layout: post
title: "Web Server"
categories: web_server
tags: web_server
---

* TOC
{:toc}

## Apache HTTP Server

File server

noindex, noarchive, nofollow, nosnippet

To disallow GPTBot:

```
User-agent: GPTBot
Disallow: /
```

Problem with the above, what if I made a website that contains content from websites that do not allow GPTBot (or others like this)?



These meta tags work in conjunction with robots.txt. With robots.txt you can give additional instructions like: `Disallow: /directory` and robots should not bother entering "directory". You'll need .htaccess to reinforce that though.

For zero-sized replies, put this in the .htaccess:

```
php_value pcre.recursion_limit 1000
php_value pcre.backtrack_limit 1000
```



## Nginx

"It is often used to serve static content, such as images and HTML files, and can also be used as a reverse proxy to distribute incoming traffic across multiple servers or to serve as a load balancer. NGINX is known for its ability to handle a large number of concurrent connections and for its fast response times, making it a popular choice for high-traffic websites and applications."



Evilginx



## Tomcat

JVM warm up

Servlet engine

"The catalina log is the global log. It is, in fact, the stdout stream for the Tomcat JVM. Tomcat's internal log statements use the java. util. logging package (juli) to log, and the default destination for that log is stdout."



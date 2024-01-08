---
layout: post
title: "Cloning Facebook"
categories: web
tags: php mysql xampp lamp html css social_media
---

<img src="https://github.com/sif/sif/raw/main/pictures/codebook.png" />

I cloned Facebook. Well, I cloned Facebook and added a little twist to it. It's called Codebook and the theme is green instead of blue. The reason I added a little twist to it was because nobody would believe me if it looked identical. 

I wanted to see how far I could go. It was pretty time consuming. The most challenging part was figuring out how I wanted to do this. Green isn't too far from blue and neither is the messaging. 

I built the entire site in XAMPP/LAMP (Linux, Apache, MySQL, PHP). That part wasn't too bad since LAMP was designed to be ready to go out of the box. I didn't use any library or framework. That wasn't needed either because it's just a simple registration box and login box. The boxes were made in PHP. The looks were done in pure HTML and CSS.  

Once the user registers, their account would be created in the MySQL database. Designing the table was interesting because I needed to think about what would happens if the same user created another account. For now, it's simple. It just has their name, birthday, email, and password.

I validate all but the email. That's something I have planned. Once you have registered, you can select "Remember me" and log in. That is based on a cookie. For the same reason I did not validate the email, I have planned for "Forgot password" to be built out. 

You log in with your email and password. Then you should be able to make some basic posts. I have a separate table for that. It's in three columns. The left side contains all of the user related stuff. The middle is the core content. The right column is for ads. 

I think most of the social media websites are built in a similar way. It was an interesting experience but I'm not sure if I want to expand on this. Maybe I could do it in Drupal and just design a theme. I could call it "Facebook Lite". 

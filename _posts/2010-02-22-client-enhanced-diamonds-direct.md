---
layout: post
title: "Client: Enhanced Diamonds Direct"
categories: client
tags: client drupal php safe_mode 
---

## Intro

This post will help anyone who suffers from the same problem while trying to setup shop with their site. It's interesting to note that safe mode is involved despite the fact that <a href="http://php.net/manual/en/features.safe-mode.php" title="Safe Mode">it's deprecated in PHP 5 and removed in PHP 6</a>.

This is more of an issue with the host than with Drupal 6 / ImageCache / Ubercart. Good thing the ImageCache folks made the D7 pledge, that way this problem is far less likely in future release.

When I encountered the problem I wanted to make sure I wasn't alone. It just makes it easier to solve problems when everyone else is experiencing the same thing.

Some people wanted to <a href="http://www.rentacoder.com/RentACoder/misc/BidRequests/ShowBidRequest.asp?lngBidRequestId=1291323" title="Drupal ImageMagick error">pay for a solution</a>.

## Problem

Only difference was that it never worked for me whereas it worked partially for him. I should note that we use D6 and similar hosting environment.

At first I figured it was permission problem (and it is by the way). I attempted that (which held off until later). So I took a stab at that and wondered my way to finding out safe mode also made my life hell even after I solved the permission problem.

Okay. So I managed to identify two problems. Permission and safe mode identified by the following errors:

<code>* warning: -----() [function.-----]: SAFE MODE Restriction in effect. The script whose uid/gid is ------/------ is not allowed to access /f5/---/public/---/sites/default/files owned by uid/gid 25000/25000 in /f5/---/public/---/---/--- on line ---. </code>

And: <em>Thumbnails does not want to be created.</em>

<code>* An image thumbnail was not able to be created.</code>

The idea was that nothing worked with safe mode.

## Solution

So. Turning off safe mode actually solved the problems. That long red horrible list gone. Wasn't something I wanted to do but I couldn't and still can't think of a better alternative that's free.

I looked deeper and found out the only solution was really to just tough it out, in regard to the safe mode issue.

In my host's forum, Zuuring (4265) posted on Wed Jan 20, 2010:

<em>I've been going through these forums, trying to get a further understanding of how to fix the PHP safe mode permission error for the savior of my wordpress website.</em>

I had to post that to laugh at his expense. alexgieg in the same thread suggested to just turn everything into "web" user/group with ssh.

Like so: <code>chgrp -R web *</code>

It was properly titled at least: <strong>PHP Safe Mode, Constant Headache</strong>

Another (in d.o node #182058) would post that good ol' Drup wants (erm, require) safe mode off.

<em>It appears your service provider has safe mode enabled and drupal wants it to be off. A number of things will not work with safe mode including upload images and files.</em>

All these years I managed without knowing that. A bit surprising, if true. But for some reason I have mine on and it works just fine.

\#182058 has a lot of good information though.

I also looked into Ubercart's forum. This guy goes (in bug report: 5256):

:D "I don't suppose you're using Drupal in private files mode, are you?"

<em>Pretty sure this is the right location to post this. Perhaps there is a fix out there but I have searched Google, Drupal forums and this forum backwards and forwards looking for a solution and I can't find it. The issue is that I have a ubercart install on a server with PHP safe mode enabled. This seems to keep users from being able to upload image files because of something that imagecache is doing with the files. Maybe the permissions are set wrong, however I've tried numerous variations with no success</em>

I still encountered problems and it was too late since during safe mode folders and files were created so I had to get that out of the way by getting the ownership back for mainly public/sites/default/files/imagecache and public/sites/default/files/imagecache/*.

I should've done this sooner and I apologize for all parties involved. A good reading for permission in this host (and similar hosting environment) would be <a href="http://blog.nearlyfreespeech.net/2007/01/28/writing-files-in-php/" title="Writing files in PHP">Writing files in PHP</a>.

Also have to love this: <a href="http://www.sarahpin.com/2008/04/18/no-human-person-ever-hated-php-safe-mode-as-much-as-i-do/" title="No human person ever hated PHP safe mode as much as I do.">No human person ever hated PHP safe mode as much as I do.</a>

I concur with gpk which he posted on October 9, 2007 - 18:47:

<strong>This is a classic problem</strong>

So to recap the solution:
<ol>
<li>Turn off safe mode.</li>
<li>Get permission.</li>
</ol>

## Final note

I should add that getting ownership back may be a difficult task. You may have to ask your host to force it. frank1985 (4097) in my host's forum post that:

<em>All you can really do is get support to change ownership back to you with a secure support request (which they'll do for free). Since this would have to happen regularly, this is clearly not the ultimate answer.</em>

I personally guess this is one of the reason why they are doing away with safe mode in the next release of PHP.

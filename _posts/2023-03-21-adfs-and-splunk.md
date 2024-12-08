---
layout: post
title: "ADFS and Splunk"
categories: splunk
tags: splunk adfs observability
---

(Originally published at: <a href="https://www.nyedis.com/post/adfs-and-splunk">ADFS and Splunk</a>)

ADFS (Active Directory Federation Services) is a perennial issue in the enterprise world. Majority of the organizations still uses ADFS for their IdM (Identity Management) needs. It integrates really well with other Microsoft products (Office 365, SharePoint, etc.) and is very customizable letting you focus on your deployment needs and policy needs.

Over the years, Microsoft have made improvements to ADFS and its associated products. It is easy to make API calls to ADFS using your favorite API tools such as SoapUI or Postman as long as you have the right credentials. Because of the growing organizational complexity, potential issues pop up everywhere to the experienced eyes.

Let’s say you have access to Splunk and you’re on Team SRE. A new product was created by your company and onboarded. This new product interacts with existing flows and multiple failure points have been identified. Currently, the one you care about is its ability to grab what it needs from the ADFS store in order to perform some critical action.

What do you do? You setup ADFS Splunk alerting! As ADFS is often in the middle interacting with both downstream and upstream flow, you can setup multiple Splunk alerts in both direction for early warning and awareness. But for now, we can just focus on the one point.

Once you have the buy-in, you can start the setup. Let’s say it was agreed that when an ADFS issue occurs, Splunk would send an email to you. For some reason, it was agreed that token expiration is a problem you want to catch.

If you do not respond within, say, 15 minutes, Splunk will send out another email. (This is why buy-inis important as it can get noisy fast, especially if it’s not well-planned.)

What kind of query would you put? Here is a real life example (fictionalized):

<code>index=”bank_department” componentID=core_ADFS_access error=123
It’s very simple as you know exactly what error you’re looking for. When you see one, you can keep your outage time in under 15 minutes.</code>

Could you write a more complicated query or catch more errors in one string? Yes. You could have something like this:

<code>(index=”bank_department” OR index=”another_bank_department” AND
index=”yet_another_bank_department”) componentID=core_ADFS_access (error=123 OR error=456)
| stats count by APPLICATION TEXT | where count > 100</code>

Sure, you can build a whole script out but you don’t want to do that. It is considered good practice to have an alert specific to the error you want it to chirp about. That way you know exactly what you’re dealing with.

If you catch 10 errors, you now have two problems, the second being “which error is this alert chirping about?” It also doesn’t allow you to designate priority to errors. For example, an ADFS issue due to network issue is not going to be prioritize by your team as that’s typically handled by another team. You could have Splunk email you every 1 hour.

You can notify the appropriate networking team and wait until the network comes back up which means the ADFS issue will recover on its own. You prioritize issues you can tackle as soon as possible. If a certificate expired, you can have your team immediately renew this.

The ability to setup good alert means you no longer need to have eyes on glass and Splunk makes SRE life that much easier.



Sifer Aseph

Cybersecurity Engineer @ Nyedis

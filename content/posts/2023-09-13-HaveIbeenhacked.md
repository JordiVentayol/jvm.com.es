---
title: "Have I been hacked?"
date: 2023-09-13T11:12:48+02:00
featured_image: ../assets/images/featured/2023-09-13-HaveIbeenhacked/img1.png
draft: true
summary: Keep data leaks under control.
description: This tool allows us to know where our data has been leaked and what data has been leaked.
author: Jordi Ventayol
authorimage: ../assets/images/global/cube_icon_background.png
categories: Blog
tags: [OSINT, LEAK, BREACHES]
---

Today I want to present to you a tool that I consider basic for investigations with data leaks. This tool is none other than https://haveibeenpwned.com/, and is developed by the famous **Troy Hunt**, of whom I leave you here the link to his personal blog where he writes different articles related to IT security (https://www.troyhunt.com/).

{{<figure src="/posts/img/2023-09-13-HaveIbeenhacked/img3.png" class="centered-image" caption="Fig.1: HIBP Portal">}}

The page has no other purpose than to collect all data leaks that occur on different websites and offer users a tool so that they can review what personal data has been leaked. The way to use it is very simple, the user has to enter their email address and the page will indicate if there is a leak from a website with that email address.

Below I show you an example of entering any email address.

{{<figure src="/posts/img/2023-09-13-HaveIbeenhacked/img2.png" class="centered-image" caption="Fig.2: Search results">}}

In the example, for each leak, we see that in **'Compromised data'** it shows us what information has been leaked and anyone can connect with the email address entered. The portal is a good tool to obtain information about a profile for which we only have the email. Through these data leaks, an attacker can begin to build a profile on an email address and obtain all kinds of information, from telephone numbers, passwords used, addresses, usernames and much more.

It is important to note that normally, and if website developers have done their job well, passwords should not be clear, but should be "protected" by a hash. This means that the attacker does not obtain our password itself, but rather obtains it as a signature from which it is not possible to execute the reverse process to obtain the password. Now, it is possible to obtain the password in the event that the signature algorithm is weak, and carry out brute force attacks to obtain the password that corresponds to the signature in question.

This is an aspect that I will explain in more detail in future articles on this blog. And we will see with examples which hash algorithms are insecure and which are not.

The problem comes when an insecure hash algorithm is used and it is a matter of time before an attacker finds the password from that hash. It is important to note that normally all other sensitive data is in clear, unencrypted form.

For this first article I just wanted to present the tool and demonstrate how easy it is for someone to collect data about us from our email. This responds to the fact that many large companies began a few years ago to hide the registration email of their users and hide it by default. Examples of them are (Facebook, LinkedIn, Instagram…)

So now you know, always try to hide the email you use to register for different websites and applications since you could be giving an attacker a huge amount of information about you. And don't forget, information is power.
---
title: "A Search Face Engine"
date: 2023-09-12T11:12:48+02:00
featured_image: ../assets/images/featured/2023-09-12-Face-Search-Engine/preview.png
draft: true
summary: Introducing PimEyes and a small security bug.
description: PimEye is a search engine that allows us to search for faces on the Internet. In their first versions they made a small security error.
author: Jordi Ventayol
authorimage: ../assets/images/global/cube_icon_background.png
categories: Blog
tags: [OSINT, HTML] 
---

For this first post we are going to get to know **PimEyes** (https://pimeyes.com/en), a very useful tool in OSINT to investigate people.

PimEyes is a page where, from a photograph, we can search the Internet for other images where the same person appears, or at least, with a face 80% similar to that of our uploaded image.

The service offers an API and the option to ask to delete any found results. From the results obtained, it seems that the tool is focused on finding compromising results about oneself, since many of the results are from pages for adults (or that apart from cats, there is a lot of content for adults on the Internet...).

{{<figure src="/posts/img/2023-09-12-Face-Search-Engine/1.PNG" class="centered-image" caption="Fig.1: PimEyes Portal">}}

In other words, we would be in front of a type of Google image search engine but with a much higher success rate. *(Yes, if you still don't know in 2020, Google allows you to search for similar images from an image uploaded by the user: https://www.google.es/imghp?hl=es)*. The only drawback, the search results are "obfuscated" in the free mode, this means that it shows us the image it has found manipulated so that we cannot enter it into another image search engine to find out its origin. In the same way, it shows us the URL of the image or video but only the first characters as shown in Fig.2.

{{<figure src="/posts/img/2023-09-12-Face-Search-Engine/model3.PNG" class="centered-image" caption="Fig.2: Locked result">}}

So if you want to take advantage of the results that the tool offers you, they offer a subscription plan for around $15 per month. But don't go yet, this is a "hacker" blog, and my mind doesn't allow me to go a little further, so I'll show you a little trick to get the original URL of the results.

The tests that I have carried out offer quite good results, it is surprising how the people in the images resemble the image used for the test. In some cases, I have even found images of the same person on a page from a photo session that was taken.
Let's go for an example with a random image. Googling this man will be our "target", I think he is a Russian model so I doubt he will ever read this post:

{{<figure src="/posts/img/2023-09-12-Face-Search-Engine/modelo1.PNG" class="centered-image" caption="Fig.3: Target">}}

So we just have to download the image and upload it to PimEyes. As you can see in Fig.4, the results are quite good and we have found different images of this person that we are unaware of but that by investigating these results we can get to know a little better.

{{<figure src="/posts/img/2023-09-12-Face-Search-Engine/model2.PNG" class="centered-image" caption="Fig.4: Search result">}}

Now we just have to right-click on the obfuscated link, and select inspect element. As you can see, the server sends the URL much less obfuscated than what is later displayed on the page, we could say that we are facing a small configuration error, which as of today (12/22/2020) from the publication of the post It is not corrected, but it would be very normal if they corrected it soon if many people use it to avoid the paid subscription.

{{<figure src="/posts/img/2023-09-12-Face-Search-Engine/model4.PNG" class="centered-image" caption="Fig.5: Inspecting element">}}

From the least obfuscated URL in the HTML element, we can enter the page and search for the image that has found us. The URL is not complete either, but through HTML at least we have the most complete URL and it is easier for us to identify where the image comes from, in case we want to continue investigating or obtain the original image.

And here the post today. Comments are welcome if anyone wants to provide more information or leave their opinion.
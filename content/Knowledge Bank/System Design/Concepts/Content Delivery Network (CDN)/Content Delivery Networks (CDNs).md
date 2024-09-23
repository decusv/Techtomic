---
title: Content Delivery Networks (CDNs)
draft: false
tags:
  - CDN
---
 A Content Delivery Network (CDN) is a distributed network of proxy servers that is used to server content from locations geographically closer to the client/user.

In terms of types of content that CDNs can serve, here are some that apply

1. Static webpages that use HTML/CSS/JS i.e., there's no server-side processing done once these files have been 'served' to the client.

 2. Media content like photos and videos.

---

## Push CDNs

Used for sites with low volume web traffic, or with sites with content that isn't often updated.

In this type of CDN, content is pushed/uploaded to the CDN. This can be done via API or a some type of file-transfer mechanism. The administrator of the website is responsible for re-uploading the content whenever it changes.

Once uploaded, you will have to update your website to link the content to the URLs provided by the CDN.

Push CDNs have higher storage needs as content has to be pushed to all edge locations belonging to the CDN and remain persistent there (based on the caching configuration)

## Pull CDNs

Used for sites with heavy traffic.

Compared to Push CDNs, pull CDNs do not require as much storage as files are requested from the origin server on demand to the nearest edge location to the user requesting the file.

The time-to-live (TTL) determines how long the content gets cached at the edge location.  Incorrectly aligning the TTL with how often the content changes means that the pull CDN will make redundant requests to retrieve the same version of the content for the users at the edge location.

---

## CDN disadvantages

CDN costs can be significant depending on the traffic. This should be weighed against how much it would cost to not use CDNs.

In pull CDNs, content might be stale if its TTL hasn't been reached, but the content has updated at the origin server. As such, the existing content is cached at the edge location which will mean the CDN could serve stale content to users requesting it until the TTL expires.

---

## Sources

1. https://www.travelblogadvice.com/technical/the-differences-between-push-and-pull-cdns/

1. https://figshare.com/articles/journal_contribution/Globally_distributed_content_delivery/6605972?file=12096455
A Content Delivery Network (CDN) is a geographically distributed network of servers that work together to deliver internet content (like web pages, images, videos) to users quickly and reliably. 

Here's a quick breakdown:

- **Goal:** Speed up content delivery for websites by bringing content closer to users.
- **How it Works:** CDNs store cached copies of website content across the globe at strategically located data centers. When a user requests content from a website, the CDN delivers it from the nearest server, reducing latency (delay).

Frameworks like [[Bootstrap]] and [jQuery](0%20-%20jQuery%20Introduction.md) can be downloaded and used. However CDN can also be used to access and use these elements without necessarily downloading them. Here are some advantages of using CDN:

- **Speed:** CDNs store cached copies of these libraries closer to users, leading to faster loading times for your website.
- **Reduced Server Load:** By using a CDN, your own server doesn't have to deliver these common libraries for every user. This frees up resources for your own website's code.
- **Reliability:** CDNs are geographically distributed, meaning if one server goes down, others can still deliver the content.

Bootstrap and jQuery can be included in your HTML code using `<link>` and `<script>` tags, respectively. These tags can point to the CDN location of the libraries.
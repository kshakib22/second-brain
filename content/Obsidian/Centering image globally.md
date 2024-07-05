Saturday, July 6th 2024, 2:49 am

**Issue**: Image centering on Obsidian doesn't translate to centering on website because custom css doesn't transfer to the site. Conversely img tag on Obsidian doesn't show the image.

Several steps to ensure all images pasted are centered properly
1. Edit the `links.ts` file in a way that the crawl function wraps any `img`, `video`, `audio`, `iframe` using `center` HTML tags. The code is linked to [[links-ts file]]
2. There was some functionality added so that the wrapping prevented an infinite recursion as well
3. Change `Files and links -> New link format -> Relative path`. Shortest path at this time glitches and doesn't work. But relative path works.

I used this following video to install Obsidian - 

- Now because of what I had to do in [Centering image globally](Centering%20image%20globally.md) , it is recommended that at ==5:48== we choose relative path instead of shortest.
- After installation, remember to change the link system in Obsidian as relative path as well!

<iframe width="676" height="337" src="https://www.youtube.com/embed/6s6DT1yN4dw" title="How to publish your notes for free with Quartz" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
 - I removed the [reading time](reading time) from sites as it was unnecessary
 - Removed timestamp from index, made custom text in other pages
 commented out
 ```ts
 if (fileData.dates) {

segments.push(formatDate(getDate(cfg, fileData)!, cfg.locale))
}
```

Replaced with -
```js
const fileName = fileData.name; // Assuming fileData has a name property

// Check if the file is not index.md
if (fileName !== 'index.md' && fileData.dates) {
  const lastUpdatedDate = formatDate(getDate(cfg, fileData)!, cfg.locale);
  segments.push(`Last updated ${lastUpdatedDate}`);
}
```

- Completely revamped the [[date settings and format]].
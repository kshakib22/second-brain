
1. Inside the quartz.config.ts I made the following changes
```ts
Plugin.CreatedModifiedDate({
priority: ["git", "frontmatter", "filesystem"],
})
```

2. In the same file
```ts
defaultDateType: "modified"
```

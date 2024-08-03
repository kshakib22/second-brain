I'm not sure why but any pdf I add with markdown doesn't work in the site. So I use the following code as a template to insert pdf as iframe HTML. Make sure the path is the correct *relative* path.

```html
<iframe src="../assets/<filename>.pdf" width="100%" height="842" style="border:none;">
    Your browser does not support iframes.
</iframe>

```

As images and iframes get centered, alignment shouldn't be an issue.
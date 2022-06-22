
# Ghost Atom Feed

An Atom feed for Ghost blogs. Ghost blogs have a built in RSS feed at the path /rss/, with this repo you can add the Atom feed standard to your blog as well.

## Usage

Go to the admin section of you Ghost blog and enter the "Labs" section. Download your current routes.yaml file and add the following section under `routes:` and upload it again.

```yaml
/atom/:
  template: atom
  content_type: application/atom+xml
```

for example:

```yaml
routes:
  /atom/:
    template: atom
    content_type: application/atom+xml

collections:
  /:
    permalink: /{slug}/
    template: index

taxonomies:
  tag: /tag/{slug}/
  author: /author/{slug}/
```

Add the atom.hbs file from this repo to the root of your favourite theme, zip the theme and upload and activate it. Your atom feed should now be available at https://yoursite.com/atom/.

Finally, go back to `Settings > Code injection` and add the following to your site header: 

```
<link href="/atom/" type="application/atom+xml" rel="alternate" title="Atom feed" />
```

So that the feed is detectable by browser feed services.

Enjoy!
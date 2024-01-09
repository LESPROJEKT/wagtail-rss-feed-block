
# Wagtail RSS feed


Wagtail RSS feed app provides custom content block that can be used with any Wagtail page model.

This way you can load any RSS feed and display it on a any Wagtail page.

## Quick start

1. Install "wagtail_rss_feed_block" using pip
    
    ```
    $ pip install <path to repo folder>
    ```

2. Add "wagtail_rss_feed_block" to your INSTALLED_APPS setting like this:

    ```
    INSTALLED_APPS = [
        ...,
        "wagtail_rss_feed_block",
    ]
    ```

3. Use RSSFeedBlock in your Wagtail Page model for example like this:

    ```
    from wagtail.models import Page
    from wagtail.fields import StreamField
    from wagtail_rss_feed_block.blocks import RSSFeedBlock

    class BlogPage(Page):
        body = StreamField([
            ...
            ('rss_feed', RSSFeedBlock()),
            ...
        ])

        content_panels = [       
            FieldPanel('body'),
        ]
    ```

4. Make and apply database migrations with new changes:

    ```
    $ python manage.py makemigrations
    $ python manage.py migrate
    ```

## Development

You can setup RSS feed block same way Quick start section does with only one difference. For local development it can be handy to install this packege in editable mode like this:

```
$ pip install -e <path to repo folder>
```


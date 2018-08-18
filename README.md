# hugo-utilitybelt
A theme consisting of partials that can be added as a theme component for any Hugo site

- `use-bootstrap4.html` is partial containing the CSS, javascript, and meta tags ideal for including bootstrap 4 (4.1.1 currently) in the `<head/>` tag of your site. This uses `async` loading of the scripts.
- `use_jquery3.html` is a partial calling the minified full jquery 3.3.1 from the CDN. This uses `async` loading of the scripts.
- `use_fontawesome5.html` is a partial for incorporating fontawesome 5 (5.1.0 currently) into your site.
- `use_fontawesome5pro.html` is a partial for incorporating fontawesome 5 (5.1.0 currently) Pro into your site.
    + Note this won't work unless you've whitelisted your site with fontawesome.
- `use_staticman.html` is a partial for providing comments
    + You will need to include in `params` `staticman_url` which contains the POST `url` e.g. https://api.staticman.net/v2/entry/eduardoboucas/staticman/gh-pages/comments and `staticman_debug`
- `use_hugo-search-index.html` is a basic partial for producing a search box and returning result if you've implemented the `hugo-search-index` project
    + This doesn't do any of the search index generation etc
- `use_snipcart_*` partials help you implement snipcart
    + See original article at <https://forestry.io/blog/snipcart-brings-ecommerce-static-site/>
    + Add to `params`: `snipcart_test_api_key` and `snipcart_live_api_key`
- `use_fullcontentrss.xml` is a partial for returning all the content in an RSS feed
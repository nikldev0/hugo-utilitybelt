# hugo-utilitybelt
A theme consisting of partials and shortcodes that can be added as a theme component for any Hugo site. This leverages the *theme composition* functionality added in Hugo v0.42.

Wanna report a bug or suggest a feature? Great stuff! For more information on how to contribute check out [our contributing guide](.github/CONTRIBUTING.md). 

Please note that this project is released with a [Contributor Code of Conduct](CODE_OF_CONDUCT.md). By participating in this project project you agree to abide by its terms.

## Usage
1. Add the `hugo-utilitybelt` as a submodule to be able to get upstream changes later `git submodule add https://github.com/lockedatapublished/hugo-utilitybelt.git themes/hugo-utilitybelt`
2. Add `hugo-utilitybelt` as a theme in your config.toml `theme = ["hugo-itsalocke", "hugo-utilitybelt"]`
3. In your custom theme or site, reference utilitybelt partials in the normal way.


## Core contents

| Partial | Description |
| --- | --- |
| [`use_bootstrap4.html`](layouts/partials/use_bootstrap4.html) | Contains the CSS, javascript, and meta tags ideal for including bootstrap 4 (4.1.1 currently) in the `<head/>` tag of your site. This uses `async` loading of the scripts. |
| [`use_jquery3.html`](layouts/partials/use_jquery3.html) | Calls the minified full jquery 3.3.1 from the CDN. This uses `async` loading of the scripts. |
| [`use_fontawesome5.html`](layouts/partials/use_fontawesome5.html) | Incorporates fontawesome 5 (5.4.1 currently) into your site. |
| [`use_fontawesome5pro.html`](layouts/partials/use_fontawesome5pro.html) | Incorporates fontawesome 5 (5.4.1 currently) Pro into your site. Won't work unless you've whitelisted your site with fontawesome.|
| [`use_staticman.html`](layouts/partials/use_staticman.html) | Provides comments. You will need to include in `params` `staticman_url` which contains the POST `url` e.g. https://api.staticman.net/v2/entry/eduardoboucas/staticman/gh-pages/comments and `staticman_debug` |
| [`use_hugo-search-index.html`](layouts/partials/use_hugo-search-index.html) | Produces a search box and returns a result if you've implemented the `hugo-search-index` project. This doesn't do any of the search index generation etc |
| [`use_fullcontentrss.xml`](layouts/partials/use_fullcontentrss.xml) | Returns all the content in an RSS feed |

- `use_snipcart_*` partials help you implement snipcart
    + See original article at <https://forestry.io/blog/snipcart-brings-ecommerce-static-site/>
    + Add to `params`: `snipcart_test_api_key` and `snipcart_live_api_key`


## Staticman
Here are the instructions for using the staticman comments system in your theme / site.

1. Add `hugo-utilitybelt` to your list of themes in `config.toml` e.g. `theme= ["hugo-utiliybelt","hugo-itsalocke"]`
2. Per the [staticman docs](https://staticman.net/docs/) add staticman to your Hugo github repo as a collaborator 
    + This enables staticman to contribute pull requests, you can alternatively create your own hosted version of staticman if you don't want to use an external dependency
3. Add a `staticman.yml` file to your site
    + Use the [samples](https://github.com/eduardoboucas/staticman/blob/master/staticman.sample.yml), consult the [docs](https://staticman.net/docs/configuration), or [lift one I made earlier](https://github.com/lockedatapublished/itsalockev2/blob/master/staticman.yml).
4. Add style functionality to your theme / site by using `use_staticman_head.html` in your `<head></head>  ` e.g. `{{ partial "use_staticman_head.html" . }}`
5. Customise comments CSS by adding a CSS file at `static/css/comments.css`
6. Include the `use_staticman.html` partial in your layouts that you wish to have comments available on.

## Snipcart
See original article at <https://forestry.io/blog/snipcart-brings-ecommerce-static-site/>

# Eventbrite
The Eventbrite shortcode allows you to embed the ticket sales page into your hugo site using the event id.

At present, only the ticket page is supported, however support for the button is on the way.

1. Add `hugo-utilitybelt` to your list of themes in `config.toml` e.g. `theme= ["hugo-utiliybelt","hugo-itsalocke"]`
2. Insert the shortcode into the page you want to sell the tickets from and set the event id e.g `{{< eventbrite event_id="0123456789" >}}`
3. Publish your page, the Eventbrite details should be listed and people can order directly from your website.

# someparts-hugo

[![Netlify Status](https://api.netlify.com/api/v1/badges/3fd1eb1a-8887-4605-a09d-d92d238aa575/deploy-status)](https://app.netlify.com/sites/someparts-hugo/deploys)

Easy to use [Hugo](https://gohugo.io/) theme to present *some parts* of a collection. It is constrained to a limited number of parts -- hence "some" in the name of this [Hugo](https://gohugo.io/) theme. Since the parts are presented in the menubar at the top of every page their number should be less than ten depending on their names (``id`` property).

[_toc_]

## Demos

- https://someparts-hugo.netlify.com/
- https://verteiltearchitekturen.de/

## Minimum Hugo version

[Hugo](https://gohugo.io/) version `0.63.2` or higher is required. 

[Installing Hugo](https://gohugo.io/getting-started/installing) explains how to prepare an environment: Either use the source if you have [go](https://golang.org/) installed or download a pre-built binaries for your OS including macOS, Windows, Linux, OpenBSD, and FreeBSD.

## Installation of the ``someparts-hugo`` theme

From the root of your site:

```
git submodule add https://github.com/tastaturtier/someparts-hugo.git themes/someparts-hugo
```

## Updating

From the root of your site:

```
git submodule update --remote --merge
```

## Run example site

From the root of `themes/someparts-hugo/exampleSite`:

```
hugo server --themesDir ../..
```

## Configuration

Copy the `config.toml` from the [`exampleSite`](https://github.com/tastaturtier/someparts-hugo/tree/master/exampleSite), then edit as desired.

## Elements of the ``someparts-hugo``-theme and how to apply them

### The Collection (``/_index.md``)
``_default`` (``list.html``)
### Menu (Drop Down)
### Icon in front of part-elements

The ``someparts-hugo``-Theme is made to present parts of a collection. The [`exampleSite`](https://github.com/tastaturtier/someparts-hugo/tree/master/exampleSite) has some colors as part of a palette. The actual usecase for which ``someparts-hugo`` was made is to [present volumes of a book series](https://verteiltearchitekturen.de/). It would be easy to adapt it to chapters of a book instead.

### Part (e.g. ``/orange/_index.md``, ``/blue.md``)

Parts 

For parts without resources it makes no difference to put it in an otherwise empty bundle (e.g. you can have the same file either as ``/blue.md`` or ``/blue/_index.md`` or ``/blue/index.md`` without any difference in the resulting ``/blue/index.html``).

This theme presents a collection of some (not too many) parts. Each part has the following meta-data that can be set in the front matter :

- **``id``**: a short name for this part to be used in the top menu and in the collection's main list view.
- **``subtitle``** [*optional*]: An optional subtitle that is only displayed on this part's main page.
- **``cover.img``**: 
- **``cover.link``** [*optional*] *(format: a URL, can be relative to this part's directory):
- **``link.url``** [*optional together with link.linktext*] *(format: a URL, can be relative to this part's directory):
- **``link.linktext``** [*optional together with link.url*] :

The following of the predefined front matter variables are suported:

- **``title``**: The title of the part that is used as the ``<h1>`` element of this part's main page as well as in the collection's main list view.
- **``aliases``** [*optional*] *(format: path)*: 
- **``audio``** [*optional*]: 
- **``cascade``** [*optional*]: 
- **``date``** [*optional*] *(format: ``2019-12-31``)*:
- **``description``**: 
- **``draft``** [*optional*]: 
- **``expiryDate
- **``headless
- **``isCJKLanguage
- **``keywords``**: 
- **``lastmod
- **``publishDate
- **``slug
- **``type
- **``url
- **``weight``**: a number that controls the order of parts in the top menu and in the collection's main list view. *Smaller* weights are *more left* in the menu and *more above* in the collection's main list view.

The following of the predefined front matter variables are not supported:

- **``images``**: has no effect
- **``layout``**: has no effect
- **``linkTitle``**
- **``markup``**
- **``outputs``**
- **``resources``**
- **``series``**
- **``summary``**
- **``videos``**
- **``tags``**, **``categories``: tags and categories are currently not supported by the ``someparts-hugo``-theme. 

In order to deactivate tags and categories the following should be included in the config.yaml (or toml or json) of your site:

    disableKinds:
    - taxonomy
    - taxonomyTerm
    - categories

### Ressource (e.g. ``/orange/something.md``)
``_default`` (``single.html``)

## Third party elements and GDPR compliance 
The ``someparts-hugo``-theme for Hugo uses the following external libraries/components:

- jQuery v3.4.1 (https://jquery.org/)
- Popper v1.14.7 (https://popper.js.org/)
- Bootstrap v4.4.1 (https://getbootstrap.com/)
- Font Awesome 4.7.0 (http://fontawesome.io)
- Cookie Consent v.3.1.0 (https://github.com/osano/cookieconsent)

They are copied to the [``static/``](static/) directory to [``css/``](static/css/), [``js/``](static/js/), and [``fonts/``](static/fonts/) because this reduces the number of involved servers for privacy reasons. However, using a CDN may have technical advantages like better caching.

### Cookie Consent / Google Analytics
[Google Analytics](https://marketingplatform.google.com/intl/de/about/analytics/) is also included. It can be switched on through the site configuration file (if ``params.googleAnalytics`` is set to a Google Analytics Tracking Id). 

The actual communication to Google will only take place if a user opts in via *Cookie Consent*.

In order to use Google Analytics you have to create an account with https://analytics.google.com/.

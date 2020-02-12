# someparts-hugo

[![Netlify Status](https://api.netlify.com/api/v1/badges/3fd1eb1a-8887-4605-a09d-d92d238aa575/deploy-status)](https://app.netlify.com/sites/someparts-hugo/deploys)

Minimalistic Hugo theme to present some parts of a collection.

## Demos

- https://someparts-hugo.netlify.com/
- https://verteiltearchitekturen.de/

## Minimum Hugo version

Hugo version `0.63.2` or higher is required. View the [Hugo releases](https://github.com/gohugoio/hugo/releases) and download the binary for your OS.

## Installation

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

## The Collection (``/_index.md``)
``_default`` (``list.html``)
## Menu (Drop Down)
## Icon in front of part-elements

The ``someparts-hugo``-Theme is made to present parts of a collection. The [`exampleSite`](https://github.com/tastaturtier/someparts-hugo/tree/master/exampleSite) has some colors as part of a palette. The actual usecase for which ``someparts-hugo`` was made is to [present volumes of a book series](https://verteiltearchitekturen.de/). It would be easy to adapt it to chapters of a book instead.

## Part (e.g. ``/orange/_index.md``, ``/blue.md``)

Parts 

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

not supported:

- **``images
- **``layout
- **``linkTitle
- **``markup
- **``outputs
- **``resources
- **``series
- **``summary
- **``videos
- **``tags
- **``categories

## Ressource (e.g. ``/orange/something.md``)
``_default`` (``single.html``)
## Cookie Consent / Google Analytics

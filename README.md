# someparts-hugo

[![Netlify Status](https://api.netlify.com/api/v1/badges/3fd1eb1a-8887-4605-a09d-d92d238aa575/deploy-status)](https://app.netlify.com/sites/someparts-hugo/deploys)

Minimalistic Hugo theme to present some parts of a collection.

## Demo

https://someparts-hugo.netlify.com/

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

## Favicons

Upload your image to [RealFaviconGenerator](https://realfavicongenerator.net/) then copy-paste the generated favicon files under `static`. 

## Override

The ``someparts-hugo``-Theme is made to present parts of a collection. The [`exampleSite`](https://github.com/tastaturtier/someparts-hugo/tree/master/exampleSite) has some colors as part of a palette. The actual usecase ``someparts-hugo`` was made is to present volumes of a book series. It would be easily possible to make it chapters of a book instead.

## Part (e.g. ``/orange/_index.md``)
### Icon in front of part-elements
## Ressource (e.g. ``/orange/something.md``)
## The Collection (``/_index.md``)
## Menu (Drop Down)
## Cookie Consent / Google Analytics

# someparts-hugo

[![Netlify Status](https://api.netlify.com/api/v1/badges/3fd1eb1a-8887-4605-a09d-d92d238aa575/deploy-status)](https://app.netlify.com/sites/someparts-hugo/deploys)

Easy to use [Hugo](https://gohugo.io/) theme to present *some parts* of a collection. It is constrained to a limited number of parts -- hence "some" in the name of this [Hugo](https://gohugo.io/) theme. Since the parts are presented in the menubar at the top of every page their number should be less than ten depending on their names (``id`` property).

---

## Overview
- [Demos](#demos)
- [Minimum Hugo version](#minimum-hugo-version)
- [Installation of the ``someparts-hugo`` theme](#installation-of-the-someparts-hugo-theme)
- [Updating](#updateing)
- [Run example site](#run-example-site)
- [Configuration](#configuration)
    - [The Collection (``/_index.md``)](#the-collection-_indexmd)
    - [Menu (Drop Down)](#menu-drop-down)
    - [Icon in front of parts](#icon-in-front-of-parts)
    - [Part (e.g. ``/orange/_index.md``, ``/blue.md``)](#part-eg-orange_indexmd-bluemd)
    - [Ressource (e.g. ``/orange/something.md``)](#ressource-eg-orangesomethingmd)
- [Third party elements and GDPR compliance](#third-party-elements-and-gdpr-compliance)
    - [Cookie Consent / Google Analytics](#cookie-consent--google-analytics)

---

## Demos

- https://someparts-hugo.netlify.com/
- https://verteiltearchitekturen.de/

The ``someparts-hugo``-Theme is made to present parts of a collection. The [`exampleSite`](https://github.com/tastaturtier/someparts-hugo/tree/master/exampleSite) has some colors as part of a palette. The actual usecase for which ``someparts-hugo`` was made is to [present volumes of a book series](https://verteiltearchitekturen.de/). It would be easy to adapt it to chapters of a book instead.

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
The collection of all the parts: All parts are presented in menu of the navigation bar at the top. Additionally there is the default home page of the site. It lists all the parts together with their keywords. If you do not provide a custom page for that you simply get the list of parts at the root of your site: ``/index.html`` or just ``/``.

You can provide a custom page that lists all the parts together with their keywords together with a headline and more information that is displayed below the headline and above the list of parts. If you want to provide such a custom page it has to be called ``/_index.md``. This page will be processed with the ``list.html`` template from the ``_default`` type.

The following predefined front matter variables are suported:

- **``title``**: will be displayed as headline
- **``aliases``** [*optional*] *(format: path)*: different paths to this page (will produce redirects)
- **``date``** [*optional*], **``lastmod``** [*optional*], **``publishDate``** [*optional*] *(format: ``2019-12-31``)*: will be used as the last modification date which is displayed at the bottom of this page. There are [rules how the lastmodified date is derived](https://gohugo.io/getting-started/configuration/#configure-front-matter). The rules proposed in the [``exampleSite/config.yaml``](exampleSite/config.yaml) state that if ``date`` metadata is set in front matter this will be the lastmodified date. If it is not provided, then information from the git configuration management system is used instead.

```
frontmatter:
  lastmod: 
    - date
    - :git
```

The content after the front matter will be displayed below the headline and above the automatically generated list of parts.

The following predefined front matter variables are not supported. Please avoid using them in the ``/_index.md`` file.

- **``audio``** 
- **``cascade``**
- **``description``**
- **``draft``**
- **``expiryDate``**
- **``headless``**
- **``images``**
- **``isCJKLanguage``**
- **``keywords``**
- **``layout``**
- **``linkTitle``**
- **``markup``**
- **``slug``**
- **``type``**
- **``outputs``**
- **``resources``**
- **``series``**
- **``summary``**
- **``url``**
- **``videos``**
- **``weight``**
- **``tags``**, **``categories``**: tags and categories are currently not supported by the ``someparts-hugo``-theme. 

In order to deactivate tags and categories the following should be included in the ``config.yaml`` (or ``.toml`` or ``.json``) of your site:

```
disableKinds:
  - taxonomy
  - taxonomyTerm
  - categories
```
### Menu (Drop Down)

The navigation bar at the top of each page displays always all the parts. If a part's page is shown the corresponding navigation bar element is shown activated.

On the left of the navigation bar is a special item. It displays the text that is configured under ``params.title`` in the ``config.yaml`` (or ``.toml`` or ``.json``) of your site. 

If you want a dropdown menu under it configure it in the ``config.yaml`` (or ``.toml`` or ``.json``) of your site:

```
params:
    dropdown: 
    - entry1:
        url: index.html
        linktext: Overview
    - divider2:
    - entry3:
        url: https://dama.io/
        linktext: External Colorist
    - divider4: 
    - entry6:
        url: imprint/
        linktext: Imprint
    - entry7:
        url: privacy/
        linktext: Privacy Policy
    - divider8:
    - entry9:
        url: index.xml
        linktext: RSS
```

The list of entries under dropdown will be used to construct te dropdown menu. Every entry that has no ``url`` or no ``linktext`` will be interpreted as an divider.

If the ``params.dropdown``  list is not set then the site tile will have a link to the home page (``/index.html``).

### Icon in front of parts

The ``someparts-hugo``-Theme is made to present parts of a collection. The [`exampleSite`](https://github.com/tastaturtier/someparts-hugo/tree/master/exampleSite) has some colors as part of a palette. The actual usecase for which ``someparts-hugo`` was made is to [present volumes of a book series](https://verteiltearchitekturen.de/). It would be easy to adapt it to chapters of a book instead.

Set ``params.icon`` in the ``config.yaml`` (or ``.toml`` or ``.json``) of your site if you want an icon in front of each  part's id (in the menu and the list of parts on the home page):

```
params.icon: <i class="fa fa-paint-brush" aria-hidden="true"></i>
```

The [Font Awesome fonts](https://fontawesome.com/) are already included in the ``someparts-hugo``-theme. There is a searchable list of icons at: https://fontawesome.com/icons?d=gallery.

If ``params.icon`` is not set, then no icon will be displayed in front of each  part's id (in the menu and the list of parts on the home page).

### Part (e.g. ``/orange/_index.md``, ``/blue.md``)

``hugo new --kind part foo`` 

... creates a new bundle in the directory ``foo/`` with a ``_index.md`` of the ``part`` type.

For parts without resources it makes no difference if it is a single file or if it is put in an otherwise empty bundle (e.g. you can have the same file either as ``/blue.md`` or ``/blue/_index.md`` or ``/blue/index.md`` without any difference in the resulting ``/blue/index.html``).

Each part has the following meta-data that can be set in the front matter :

- **``id``**: a short name for this part to be used in the top menu and in the collection's main list view.
- **``private``** [*optional*]: if ``true`` the part *will not be* displayed on navbar, homepage, sitemap, and RSS. If ``false`` or not set the part *will* be included in navbar, homepage, sitemap, and RSS.
- **``subtitle``** [*optional*]: An optional subtitle that is only displayed on this part's main page.
- **``cover.img``**: Path to an image that will be displayed on the right side of this part's page.
- **``cover.link``** [*optional*]: A URL (relative path from this part's page or an abolute URL) that is used as an href on the cover image that will be displayed on the right side of this part's page.
- **``link.url``** [*optional together with link.linktext*]: A URL (relative path from this part's page or an abolute URL) that will be used as href for the link shown below the description of the part on this part's page. If ``link.url`` is set ``link.linktext`` has also to be set.
- **``link.linktext``** [*optional together with link.url*]: Text that will be shown below the description of the part on this part's page. If ``link.linktext`` is set ``link.url`` has also to be set.

The following of the predefined front matter variables are suported:

- **``title``**: The title of the part that is used as the ``<h1>`` element of this part's main page as well as in the collection's main list view.
- **``aliases``** [*optional*] *(format: path)*: different paths to this page (will produce redirects)
- **``description``**: a text that is displayed on the left side on the part's page (left of the cover image).
- **``keywords``**: will be displayed on the collection's page (the home page) below the link to the part's page.
- **``type``**: must be ``part``
- **``weight``**: a number that controls the order of parts in the top menu and in the collection's main list view. *Smaller* weights are *more left* in the menu and *more above* in the collection's main list view.
- **``date``** [*optional*], **``lastmod``** [*optional*], **``publishDate``** [*optional*] *(format: ``2019-12-31``)*: will be used as the last modification date which is displayed at the bottom of this page. There are [rules how the lastmodified date is derived](https://gohugo.io/getting-started/configuration/#configure-front-matter). The rules proposed in the [``exampleSite/config.yaml``](exampleSite/config.yaml) state that if ``date`` metadata is set in front matter this will be the lastmodified date. If it is not provided, then information from the git configuration management system is used instead.

```
frontmatter:
  lastmod: 
    - date
    - :git
```

The content after the front matter will be displayed below description (left) and cover image (right) of this part's page. If this part has ressources  the automatically generated list of them will be shown below the content.

The following of the predefined front matter variables are not supported and should not be used in the front matter of a part page:

- **``audio``**
- **``cascade``** 
- **``draft``** 
- **``expiryDate``**
- **``headless``**
- **``images``**
- **``isCJKLanguage``**
- **``layout``**
- **``linkTitle``**
- **``markup``**
- **``outputs``**
- **``resources``**
- **``series``**
- **``slug``**
- **``summary``**
- **``url``**
- **``videos``**
- **``tags``**, **``categories``: tags and categories are currently not supported by the ``someparts-hugo``-theme. 

In order to deactivate tags and categories the following should be included in the ``config.yaml`` (or ``.toml`` or ``.json``) of your site:

```
disableKinds:
  - taxonomy
  - taxonomyTerm
  - categories
```

### Resource (e.g. ``/orange/something.md``)
All regular pages i.e. pages that are not ``_index.md`` or ``index.md`` (e.g. ``/orange/something.md``) will be rendered using the ``_default`` type ``single.html`` template. Often these are pages that belong to a certain part and are in this sense resources of this part. They work only if the part is represented as a bundle (i.e. a folder containing ``_index.md`` of type ``part``). In that case all resources will be displayed below that parts description on the part's page.

If there is a part called ``foo`` that is a bundle (i.e. ``/foo/_index.md``) you can create resources for the ``foo`` part with the command

```
hugo new --kind resource foo/bar.md
```

This makes a new file ``/foo/bar.md``  alongside ``/foo/_index.md``. Further resource pages can be created for the same part:

```
hugo new --kind resource foo/baz.md
```

results in the new file ``/foo/baz.md``  alongside ``/foo/_index.md`` and ``/foo/bar.md``. 

There can be other pages that are not resources of a part because they are not part of a bundle (e.g. ``/privacy.md``). A ``weight`` property defined in the front matter of it would then have no effect. 

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

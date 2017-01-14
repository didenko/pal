# PAL

**P**hoto **AL**bum (PAL) is a gallery/photoblog theme for Hugo.

It is a fork of the [Phugo theme](https://github.com/aerohub/phugo) which by itself is a port of [HTML5 UP Multiverse template](https://html5up.net/multiverse).

## Screenshot

![screenshot](./images/screenshot.png)

## Features

### Original

- Fully Responsive
- HTML5 + CSS3
- FontAwesome icons
- Compatible with all modern browsers

### Added

- One level albums support
- Google Analytics
- Working contact form
- Unlisted albums
[]: // (- Basic breadcrumbs)

## Demo

http://didenko.com/

## Contents

- [Installation](#installation)
- [Configuration](#configuration)
- [Posting](#posting)
- [Test your site](#test-your-site)
- [Building the site](#building-the-site)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)


## Installation

- [Install Hugo](//gohugo.io/overview/installing/) and create a new site.
- Install `pal`. To do that, run while in the root directory of your new Hugo project:

```
$ git clone https://github.com/didenko/pal themes/pal
```

- Take a look inside the [`exampleSite`](./exampleSite) folder of this theme. You will find a file called [`config.toml`](./exampleSite/config.toml). Copy the `config.toml` into the root folder of your Hugo site.

## Configuration

Open just-copied `config.toml` and fill it with your data. Pay attention on instructions for the contact form. Commenting out **all** `params.footer.contact` configuration sections will avoid rendering the contact form.

Here is the list of all configuration options used by the theme:

- **[**params**]**:
    description,
    author,
    keywords,
- **[[**params.header.links**]]**:
    name,
    url,
    icon
- **[**params.footer.paragraph**]**:
    headline,
    text
- **[**params.footer.links**]**:
    target
- **[**params.footer.social**]**:
    headline
- **[[**params.footer.social.links**]]**:
    url,
    icon,
    label
- **[**params.footer.copyright**]**:
    name
- **[**params.footer.contact**]**:
    headline,
    realEmail,
    buttonText,
    resetText
- **[**params.footer.contact.name**]**:
    warning,
    text
- **[**params.footer.contact.email**]**:
    warning,
    text
- **[**params.footer.contact.message**]**:
    warning,
    text

## Posting

Now you are ready to create your first photo album. Albums consist of full-resolution images, a smaller resolution thumbnails for the images and a decriptor file used by `Hugo` to generate the web page and point to the images and thumbnails.

it is up to you where to store the images and thumbnails, as long as they can be accessible via a URL from a client browser. I keep them in the `static/albums/` folder of a `Hugo` project, so they end up in the `/albums/` path of a generated website.

Album's index files have to be in the `content/` directory hierarchy. To generate an album descriptor run the following inside your project:

```
$ hugo new YOUR-ALBUM.md
```
It will create an index file of your first album. Open `content/YOUR-ALBUM.md` with your text editor. You will see something like this:

```
+++
albumthumb = "path/to/album/cover/image"
date = "2016-10-21T19:07:17+03:00"
title = "index"
type = "pal"
# unlisted = "yes"
+++

{{< photo full="path/to/first/FULL-SIZE/image/in/your/gallery.jpg" thumb="path/to/its/THUMBNAIL/image.jpg" alt="" phototitle="SOME TITLE" description="SOME SHORT DESCRIPTION. MARKDOWN **SUPPORTED**. REPEAT THIS SHORTCODE FOR EVERY IMAGE YOU HAVE IN THIS GALLERY">}}

```
Change the title of your album and set the url of album's cover. Then fill the shortcode fields with the first image data. Repeat the shortcode for every image in the gallery. You may use both local and remote images.

If you uncomment the `unlisted` parameter, then the album will be rendered into a web page, but will not be a part of the list of albums on the home page.

Repeat the images/thumbnails/descriptor process for all desired albums. 

## Test your site

In order to see your site in action, run Hugo's built-in local server. 

    $ hugo -v server -w

Now enter `localhost:1313` in the address bar of your browser.

## Building the site

To put the generated website files into the `public` folder in the Hugo project root, run:

    $ hugo

Alternatively, to put the generated website files into a specific outside directory, run:

    $ hugo -d PATH_TO_PUT_WEBSITE_FILES_TO

## Contributing

Did you found a bug or got an idea? Feel free to use the [issue tracker](//github.com/didenko/pal/issues).

## License

The original templates are released under the Creative Commons Attribution 3.0 License. Please keep attribution links to the original templates when using for your own project.

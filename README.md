# Bold/Windstone Image Gallery

This folder contains two basic image gallery implementations.

* `index.hml` - This contains the gallery implemented within the wrapper
  that's used the Squarespace site. If you use this page you'll need to
  keep the wrapper up to date as you make changes to the main site.
* `index_bare.html` - This is a bare bones implementation of the gallery
  that would be suitable to include in an `iframe` inside the
  Squarespace site.

## Adding images to the gallery

In each html file there's a "center" section containing the slides. It
looks something like this:

```html
<!-- SLIDES -->
<div class="slide prev_2" data-mightyslider="
cover: 'images/3200+Rolling+Woods+Dr-1.jpg',
thumbnail: 'images/3200+Rolling+Woods+Dr-1_thumb.jpg'
"></div>

<div class="slide prev_1" data-mightyslider="
cover: 'images/3805_Montelena_Cir-2.jpg',
thumbnail: 'images/3805_Montelena_Cir-2_thumb.jpg'
"></div>

<div class="slide active" data-mightyslider="
cover: 'images/3_660_turkey_run_ct__norman__ok_73026__usa_49.jpg',
thumbnail: 'images/3_660_turkey_run_ct__norman__ok_73026__usa_49_thumb.jpg'
"></div>

<div class="slide next_1" data-mightyslider="
cover: 'images/4210_Frontier_Trail-6.jpg',
thumbnail: 'images/4210_Frontier_Trail-6_thumb.jpg'
"></div>

<div class="slide next_2" data-mightyslider="
cover: 'images/5921_Windstone_Drive_-12.jpg',
thumbnail: 'images/5921_Windstone_Drive_-12_thumb.jpg'
"></div>
<!-- END OF SLIDES -->
```

To add slides put the images that you want to use in the `images`
folder, and then duplicate (or modify) a `div`, changing the `cover` and
`thumbnail` attributes to point to your new image.

Thumnail images should be cropped to square and at a size of 80x80.

## Changing the aspect ratio of slides

To change the aspect ratio adjust the `height` and `width` atrributes in
the block that looks like this:

```html
<div class="frame" data-mightyslider="
width: 1585,
height: 800
">
```

## Adding new galleries

Duplicate one of the html pages with a new filename and make
changes to the new file.

## Working with these files locally

Most web browsers will not load JavaScript and CSS resources on pages
that exist on the local disk. So you'll need to use some sort of
webserver to serve the pages to your browser.

One good solution is the "Web Server for Chrome" add-on: <https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb?hl=en>

Another option, if you're comfortable with command line tools is the
`http-server` package for npm.

To install it:

```
npm install http-server -g
```

And then change directories into the one that you want to serve and run
the server.

```
cd bold-windstone
http-server
```

You should see some output indicating where you can find your page.
(Something like <http://127.0.0.1:8080/>)

## Serving these files publicly

To make these galleries public you'll need to post themt to a web server
of some sort.

If you have an Amazon Web Services account S3 (with or without
CloudFront) might be a good option.

Other services that I'm aware of, but have not used (and cannot vouch
for) include:

* <https://www.netlify.com/>
* <https://getforge.com/>

A "traditional" FTP based web host would also do the trick.


[![LICENSE](https://img.shields.io/badge/license-MIT-lightgrey.svg)](https://raw.githubusercontent.com/namiltd/bootstrap-ie/master/LICENSE)
[![Tip Me via PayPal](https://img.shields.io/badge/PayPal-tip%20me-green.svg?logo=paypal)](https://www.paypal.me/namiltd)
[![NPM Downloads](https://img.shields.io/npm/dt/bootstrap-ie.svg)](https://www.npmjs.com/package/bootstrap-ie)
[![](https://data.jsdelivr.com/v1/package/gh/namiltd/bootstrap-ie/badge)](https://www.jsdelivr.com/package/gh/namiltd/bootstrap-ie)
[![github-stars-image](https://img.shields.io/github/stars/namiltd/bootstrap-ie.svg?label=github%20stars)](https://github.com/namiltd/bootstrap-ie)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)

# Bootstrap 4 compatibility module for IE8 and IE9

Bootstrap 4 drops support for Internet Explorer 8 and 9, but you can add it back by simply adding a conditional statement targeting IE 8 and 9 with a CSS file and a CDN-hosted JavaScript file to polyfill HTML5 element support.

### Quick start
Several quick start options are available:
- Download the latest release from https://github.com/namiltd/bootstrap-ie/releases
- Clone the repo `git clone https://github.com/namiltd/bootstrap-ie.git`
- Install with [npm](https://www.npmjs.com/package/bootstrap-ie) `npm install bootstrap-ie`
- Install wuth [yarn](https://yarnpkg.com/en/package/bootstrap-ie) `yarn add bootstrap-ie`
- Install with [Composer](https://getcomposer.org/) `composer require namiltd/bootstrap-ie`

### Usage

1.  Add `<meta http-equiv="x-ua-compatible" content="ie=edge">` to the top of the <head> of your page

2.  Add the following conditional statements to the `<head>`:

```html
    <link href="css/bootstrap.min.css" rel="stylesheet">
    <!--[if IE 9]>
      <link href="css/bootstrap-ie9.min.css" rel="stylesheet">
      <script src="https://cdn.jsdelivr.net/gh/namiltd/bootstrap-ie/js/bootstrap-ie9.js"></script>
    <![endif]-->
    <!--[if lte IE 8]>
      <link href="css/bootstrap-ie8.min.css" rel="stylesheet">
      <script src="https://cdn.jsdelivr.net/g/html5shiv@3.7.3"></script>
      <script src="https://cdn.jsdelivr.net/gh/namiltd/bootstrap-ie/js/bootstrap-ie8.js"></script>
    <![endif]-->
```

If you are using the bootstrap.js code add the following to the footer:

```html
  <!--[if gte IE 9]><!-->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.4/umd/popper.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js"></script>
  <!--<![endif]-->
  <!--[if lte IE 8]>
    <script src="https://code.jquery.com/jquery-1.12.4.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.js"></script>
  <![endif]-->
```

This will load jQuery, PopperJS and Bootstrap as normal on all browsers other than IE8.
IE8 will load the latest compatible version of jQuery and the unminified Bootstrap JS (the minified version causes an error).

### FAQS

**Q. What does this fix/polyfill?**

A. Internet Explorer 9 doesn't support flexbox so there is a float-based layout fallback and a couple of other minor fixes. Internet Explorer 8 doesn't support rem units and media queries. The bootstrap-ie8.js module fixes this.

**Q. Is the CSS hosted on a CDN?**

A. No. Caution! Scripts bootstrap-ie8.js and bootstrap-ie9.js works by requesting a pristine copy of your CSS via AJAX, so if you host your stylesheets on a CDN (or a subdomain), you'll need to set up a local proxy to request the CSS for old IE browsers. Prior versions recommended a deprecated x-domain approach, but a local proxy is preferable (for performance and security reasons) to attempting to work around the cross-domain limitations.

**Q. Will you provide LESS/SASS files?**

A. Maybe in a future release I'll provide SASS file (with comments).

**Q. Do I need the RespondJS polyfill for IE8 like Bootstrap 3 uses?**

A. No, bootstrap-ie8 includes RespondJS polyfill for IE8.

**Q. Where can I see a demo?**

A. Right here: [http://namiltd.github.io/bootstrap-ie/test.htm](http://namiltd.github.io/bootstrap-ie/test.htm)

**Q. I don't have access to IE8/IE9 browser to test- how can I see how my site appears?**

A. You could use free [Multi-Browser Screenshots Chrome Extension](https://chrome.google.com/webstore/detail/multi-browser-screenshots/dhaknibfbngnmflbejdkliedmjmbjojk) to see screenshots of any webpage.

### Known Issues

- There are various problems with the use of the JavaScript Bootstrap 4 in IE8. So far dropdowns and modal dialogs have been run.
- View a list of known issues at [https://github.com/namiltd/bootstrap-ie/issues](https://github.com/namiltd/bootstrap-ie/issues)

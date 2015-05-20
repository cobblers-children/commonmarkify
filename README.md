# Markdownify

The simplest markdown editor with built in cloudinary image upload.

Based on CodeMirror for the editor and Marked for the preview.

# Demo:

[tibastral.github.io/markdownify](http://tibastral.github.io/markdownify/)

# Usage:
Lets say you have a textarea you want to markdownify.

# Install with bower:

```sh
bower install jquery.markdownify
```

```html
<textarea class='markdown' id="markdown"></textarea>
```

```js
$('.markdown').markdownify();
```

You can then add buttons for convenience of your users.
You need to encapsulate your links (or buttons) in a item with the 'markdownify-menu' class. The data-target attribute is the id of the textarea you want to control.

```html
<div class='markdownify-menu' data-target='markdown'>
  <a class='btn--insert' data-prefix='*' data-suffix='*' href='javascript:void(0)'>i</a>
  <a class='btn--insert' data-prefix='**' data-suffix='**' href='javascript:void(0)'>b</a>
  <a class='btn--insert' data-prefix='# ' href='javascript:void(0)'>h1</a>
  <a class='btn--insert' data-prefix='## ' href='javascript:void(0)'>h2</a>
  <a class='btn--insert' data-prefix='> ' href='javascript:void(0)'>quote</a>
  <a class='btn--insert' data-prefix='* ' href='javascript:void(0)'>list</a>
  <a class='btn--insert' data-prefix='1. ' href='javascript:void(0)'>1.</a>
  <a class='btn--insert' data-type='link' href='javascript:void(0)'>link</a>
</div>
```

To upload an image directly to cloudinary, you can add add a param to markdownify :

```js
$('.markdown').markdownify(
  cloudinary: {
    // create an account on cloudinary and put here your cloud name
    cloudName: 'YOUR_CLOUD_NAME',
    // get your unsigned uploading key
    // http://cloudinary.com/blog/direct_upload_made_easy_from_browser_or_mobile_app_to_the_cloud)
    unsignedUploadingKey: 'YOUR_UNSIGNED_UPLOADING_KEY'
  }
);
```

# Options
If you want the preview toggle, add this after your markdown editor HTML:

```html
<div class='markdown-preview'></div>
<a class='btn--preview' href='javascript:void(0)' data-target='markdown'>preview</a>
```
T
If you want the edit/preview button text to be different, modify the following:

_Change Edit button text:_
Add the following attribute to the preview button:
```html
data-toggle-text='edit-non-default-text'
```
_Change Preview button text:_
Modify the default text that's within the <a> tag:
```html
<a class='btn--preview' href='javascript:void(0)' data-target='markdown'>edit me here</a>
```

The code is extracted from [mipise.com](https://mipise.com) and extensively used in [jobboardmaker.com](https://jobboardmaker.com)

# Bootstrap Message Box plugin for jQuery
## About
This jQuery plugin creates DIV for messgae box using Bootstrap and uses jQuery.modal to show, hide and remove it from DOM. It uses icons for message from Glyphicons or FontAwesome.
## Features
1. Shows message box by only one jQuery function
2. Message have a title
3. Message could have an icon (after include [Glyphicons] or [FontAwesome])
4. Supports many buttons (not only "Close")
5. You can use onclick event handler for your buttons
5. Customizable (header, text, icons and buttons)

## Requirements
This plugin requires [Bootstrap v.3.3.6] or later (it includes jQuery). Needs [Glyphicons] or [FontAwesome] for show icon.

## Getting Started
To get started, add the following JavaScript script *jquery.bs.msgbox.js*. As Message Box is jQuery plugin for Bootstrap - some additional dependencies are required.

In examples below, replace **path** with the path to the folder where *jquery.bs.msgbox.js* is kept:
```html
<script src="path/jquery.min.js"></script>
<script src="path/bootstrap.min.js"></script>
<script src="path/jquery.bs.msgbox.js"></script>
```
Add function that shows message box:
```html
<script type="text/javascript">
    var show=function() {
        jQuery(function($){
            $('body').bsMsgBox({
                title: "Simple title",
                text: "This is a text",
                icon: 'ok'
            });
        });
    }
</script>
```
Add HTML with button on any way to call function *show()*:
```html
<button type="button" class="btn btn-primary" onclick="show()">Show Message Box</button>
```
As result after clicking on button you will see message box.

![Simple message box](http://mokhin-tech.ru/images/bsmsgbox/msgbox1.png)

Click on times-icon in header or "Close" button to hide message box.

## Examples
### Message box with times-icon and big title
```js
$('body').bsMsgBox({
    title: "Simple title",
    text: "This is a text",
    icon: 'error',
    titletag: '<h1>'
});
```
![Message box with times-icon and big title](http://mokhin-tech.ru/images/bsmsgbox/msgbox2.png)
### Change style of "Close" button
```js
$('body').bsMsgBox({
    title: "Simple title",
    text: "This is a text",
    icon: "question",
    buttons: {
    close: {
        type: "success"
        }
    }
});
```
![Change style of "Close" button](http://mokhin-tech.ru/images/bsmsgbox/msgbox3.png)
### Additional button
```js
$('body').bsMsgBox({
    title: "Simple title",
    text: "This is a text",
    icon: "info",
    buttons: {
        button1: {
        text: "Another one"
        }
    }
});
```
![Additional button](http://mokhin-tech.ru/images/bsmsgbox/msgbox4.png)

As you see, there are two buttons and only "Close" button closes modal. Last one do nothing.
### Additional button: adding 'onclick' event handler
First, add *f1* function to your HTML page:
```js
var f1=function() {
    alert("It's work");
};
```
Then use
```js
$('body').bsMsgBox({
    title: "Simple title",
    text: "This is a text",
    icon: "info",
    buttons: {
        button1: {
        text: "Another one",
        onclick: "f1()"
        }
    }
});
```
After clicking on "Another one" button you see alert message.
![Additional button](http://mokhin-tech.ru/images/bsmsgbox/msgbox5.png)

## Copyright
&copy; 2015-2016 Denis Mokhin; please, visit http://mokhin-tech.ru. This plug-in is under GNU/GPL v2 or later; please visit http://www.gnu.org/licenses/old-licenses/gpl-2.0.html

## Contributing, help and TODO
What I'm goin' to do next:
* Fix, if no icon selected (no media-list template should be used)
* Add size of modal (modal-sm or modal-lg)
* Add gettin text via AJAX functionality (when point url)
* Add custom icons support (Glyphicons or Font Awesome, not only 'ok', 'info', 'qestion' or 'error')

[Glyphicons]: http://glyphicons.com/
[FontAwesome]: http://fontawesome.io/
[Bootstrap v.3.3.6]: http://getbootstrap.com/ "Bootstrap v.3.3.6"

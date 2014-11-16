CustomScrollbar.js
==================

## A script for custom styled browser scrollbars

CustomScrollbar.js is a small script allows you to style the vertical scrollbar of the entire web page by using CSS. You can adjust the appearance of the scrollbar background and the scroll thumbs that include arrows for scrolling up and down. Here are some key facts that should provide a short overview of what CustomScrollbar.js is and how it works:

* Easy to use and simple configuration
* Fully customizable via CSS
* Usage of browsers' default scroll behavior
* Cross-browser and multi-system support
* Native scrolling on mobile devices
* No external dependencies


As you can see the script makes use of the default browser scroll behavior. This means that no kinetic scrolling or real-time calculations are needed. CustomScrollbar.js simply hides the native window scrollbars and adds a custom overlay to the web page. The script is well tested on different platforms and browsers including Windows, Mac OS X, iOS, Android and mobile devices like Android smartphones and tablets, iPhone/iPad and Microsoft Surface. For mobile devices there is a small device detection which disables CustomScrollbar.js since you normally want to make use of the native mobile scrolling on that devices.

## Demo
You can check the <a href="http://matthias-schuetz.github.com/customscrollbar.js">example.html</a> that is included in this package. This is also the website of CustomScrollbar.js.

## Usage

Just include the file "CustomScrollbar.js" in your HTML code and create an instance of the CustomScrollbar function.

### HTML

```html
<html>
	<head></head>

	<body>
    	Content
    
		<script src="CustomScrollbar.js" type="text/javascript"></script>
		<script type="text/javascript">
			var scrollbar = CustomScrollbar({
				thumbHeight: 40
			});
		</script>
    </body>
</html>
```

### JavaScript

```javascript
/*
 * CustomScrollbar.js
 * 
 * @param Number thumbHeight Height of the scrollbar (percent of window height)
 * @param Number bodyPaddingRight Optional: additional padding on the right side
 * @param Object selectors Optional: IDs for scrollbar and scrollbar thumb
 */

var scrollbar = CustomScrollbar({
    thumbHeight: 40,
    bodyPaddingRight: 10,
    selectors: {
		scrollbar: "scrollbar",
		scrollbarThumb: "scrollthumb"
	}
});
```

### CSS

```css
html::-webkit-scrollbar {
	width:0 !important;
}

#scrollbar {
	position:absolute;
	top:0;
	right:0;
	height:100%;
	width:20px;
	background-color:#272b2f;
	z-index:2;
}

#scrollthumb {
	position:absolute;
	top:0;
	right:0;
	width:20px;
	background:#e94525;
}

#scrollthumb:before {
	position:absolute;
	top:0;
	left:0;
	width:20px;
	height:20px;
	background-image:url("../assets/arrows.png");
	background-repeat:no-repeat;
	background-position:0 0;
	content:"";
	display:block;
}

#scrollthumb:after {
	position:absolute;
	bottom:0;
	left:0;
	width:20px;
	height:20px;
	background-image:url("../assets/arrows.png");
	background-repeat:no-repeat;
	background-position:0 -20px;
	content:"";
	display:block;
}
```

In this example there are transparent PNG images that are used for the appearance of the arrows but you could also use a custom icon font or SVG.

## Notes

One last thing is to mention that the scrollbar should at least have a width of 18px since the native scrollbar in Firefox on Windows is still fully visible but gets overlapped of the custom scrollbar. It's also important to know that the script only generates a vertical scrollbar since it was developed with responsiveness in mind. The era of horizontal scrollbars has come to an end so it shouldn't be necessary to support this element anymore.

## License

CustomScrollbar.js is released under the MIT license.
# NavScroll

NavScroll is a simple jQuery plugin for animated scrolling to a section of your page. It also features mobile dropdown support so if your navigation transforms into a dropdown on a certain breakpoint, navScroll hides the dropdown after a click.

# Demo

There's a demo included with this package. It's an example of navigation I use a lot, so feel free to use it yourself! <br>
You can also checkout the demo here: [jhammann.github.io/jquery-navScroll/demo/](http://jhammann.github.io/jquery-navScroll/demo/)

# Setup

Include a recent version of jQuery and the navScroll plugin inside your page.

```html
<script src="http://code.jquery.com/jquery-1.11.0.min.js"></script>
<script src="jquery.navScroll.js"></script>
<script>
  // To attach navScroll to an element without mobile dropdown support
  $('.nav').navScroll();

  // Or you can enable mobile dropdown support and give it a custom breakpoint (defaults to 1024)
  $('.nav').navScroll({
    mobileDropdown: true,
    mobileBreakpoint: 768
  });
</script>
```

#Options

| Name | Description | Type | Default |
|------|-------------|------|---------|
| `scrollTime` | The time it takes to scroll to the element in milliseconds (set this to 0 so it obviously won't show an animation). | Integer | 500 |
| `navItemClassName` | The class of the items which invokes the scroll animation. All anchor tags inside the element are clickable when the value is empty. | String | '' |
| `navHeight` | Set the height of the navigation (to use as offset). 'auto' let's the plugin determine the height automatically, a number determines the height in px. | Integer or String | 'auto' |
| `mobileDropdown` | If your navigation hides and is used as a dropdown on small screens setting this to true hides the dropdown after a click. | Boolean | false |
| `mobileDropdownClassName` | Additionaly you can insert the mobile nav's classname here, when left empty the plugin searches for a `<ul>` in the same parent element. | String | '' |
| `mobileBreakpoint` | The 'mobile' breakpoint (like the max-width of a media query). It's recommended that you check this if you use mobile dropdown support. | Integer | 1024 |

### Specific scrollTime

The scrollTime option is for all `<a>` tags inside the element on which navScroll is called. If you want different scrollTimes for different anchors you have to include the data-attribute `data-scrolltime`. The value should be a number. The 'Section 3' URL in the [demo](http://jhammann.github.io/jquery-navScroll/demo/) is an example of this.

#Changelog

### Version 1.1.0

* Added support for the scrollTime data attribute.

### Version 1.1.1

* [Bugfix] Clicking on `<a>` tags without a leading `#` in the href attribute now navigates you to the actual path and won't return an error.
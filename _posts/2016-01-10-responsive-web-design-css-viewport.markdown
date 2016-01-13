---
title:  "Responsive Web Design Using CSS Viewport"
date:   2016-01-10 12:38:03 -0500
categories: 
 - CSS
 - Design
permalink: responsive-web-design-css-viewport

---
Designing mobile first isn’t just a trend, it’s a principle. When the size of your canvas is undefined, design constraints can be a challenge. With CSS3, those constraints become more concrete with view height `vh` and view width `vw`.  

Before designing any mobile first site, include the tag: 

{% highlight html %}
<meta name="viewport" content="width=device-width, initial-scale=1"> 
{% endhighlight %}

This meta tag is one of the most important parts of mobile design.  It scales the width of a webpage to the device that's viewing it. Without it, the content will render as it would on a desktop and force mobile users to zoom in.

Starting with this tag is considered best practice, and it unlocks one of the best parts of CSS3, viewport height `vh` and width `vw`.  `1vh/vw` translates into 1/100th of the viewport's height/width. 

Say we want a fullscreen background image.  We could define the height in pixels but the result would vary depending on the device. One easy solution is to declare:

{% highlight html %}
<div class="bannerpic"></div>
{% endhighlight %}

{% highlight css %}
.bannerpic {
    background-image: url("http://carterrink.com/clouds.jpg");
    height: 100vh;
    width: 100vw;
}
{% endhighlight %}

Using the view height and view width sizing units, we ensure that the background image will stretch across the height and width of the viewport.<br><br>

<p data-height="581" data-theme-id="0" data-slug-hash="pgwPbP" data-default-tab="result" data-user="cartuhok" class='codepen'>See the Pen <a href='http://codepen.io/cartuhok/pen/pgwPbP/'>pgwPbP</a> by cartuhok (<a href='http://codepen.io/cartuhok'>@cartuhok</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

<br>

Before using these units, it's important to note that there are certain browser restrictions.  According to [can I use it][can-I-use-it], IE10, 11 and Microsoft Edge do not support the `vmax` unit. `1vmax` represents `1vh` or `1vw`, whichever is larger. In other words, `1vmax` equals `1vh` in portrait mode, and `1vw` in landscape.  The opposite is true for `vmin`.  It's also important to note that in IE9, the syntax `vm` is used instead of `vmin`.  Opera Mini is not supported at all. 

With the introduction of these sizing units in CSS3, designing for different viewports is a little less of a hassle. Try using them in your next project to ensure a more uniform user expirence across devices.


[can-I-use-it]: http://caniuse.com/#search=vh

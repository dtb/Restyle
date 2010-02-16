CSS Resets with Sensible Defaults: a Minimal CSS Framework
==========================================================

CSS resets have become important in the web developer's toolkit. These handy little files clear out inconsistent default styles across browsers, giving us as developers greater control over the final look of our pages, and forcing us to define our own styles, rather than lazily relying on inconsistent browser defaults. If you're new to the concept of reset stylesheets, [Six Revisions][sr-home] has a [great introduction][reset-intro] to the concept, including some examples of the inconsistencies in cross-browser default styling.

I've done a lot of work with css on my blog and some client sites in the past few weeks, and in the process, pondering CSS resets. I use the popular [reset stylesheet][eric-reset] published by [Eric Meyer][eric], because it's small and light, and in the public domain. I'm very happy with it as a reset, but I've been struck by one of the drawbacks of CSS resets: CSS resets give us greater consistency, at the cost of greater work required to style a page. I believe CSS frameworks such as [Blueprint][] and [960 gs][] attempt to correct this, but in my experience, these are actually much harder to develop with than starting from scratch. I'm pretty good with CSS, and find that when I develop with a CSS framework, I spend a great deal of time reverting styles applied by the framework. This not only requires more time on my part, it also makes my CSS harder to maintain.

As a result of these issues, I often find myself using a reset stylesheet and just hand coding all of my CSS from the ground up. This has a few problems:
- I'm repeating a large amount of work from one site to the next to get hum-drum basic styles working and 
- I tend to forgot to style certain elements (`code`, `abbr`, `del`, etc.). 
Fed up with this, I decided to create a stylesheet that would first reset browser defaults, and then apply sensible defaults to them. This stylesheet would serve a similar purpose to the user-agent stylesheet provide by a browser, except that it would be consistent across browsers. 

[sr-home]: http://sixrevisions.com/
[reset-intro]: http://sixrevisions.com/css/css-tips/css-tip-1-resetting-your-styles-with-css-reset/
[eric-reset]: http://meyerweb.com/eric/tools/css/reset/
[eric]: http://meyerweb.com/
[blueprint]: http://www.blueprintcss.org/
[960 gs]: http://960.gs/

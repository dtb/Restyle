CSS Resets with Sensible Defaults: a Minimal CSS Framework
==========================================================

A CSS reset is a stylesheet that clears out inconsistent default styles across browsers. This gives us as developers greater control over the final look of our pages, and forces us to define our own styles, rather than lazily relying on inconsistent browser defaults. If you're new to the concept of reset stylesheets, [Six Revisions][sr-home] has a [great introduction][reset-intro] to the concept, including some examples of the inconsistencies in cross-browser default styling.

I've done a lot of work with CSS in the past few weeks, and in the process, I've been pondering CSS resets. I use the popular [reset stylesheet][eric-reset] published by [Eric Meyer][eric], because it's small and light, and in the public domain. I'm very happy with it as a reset, but I've been struck by one of the drawbacks of CSS resets: CSS resets give us greater consistency, at the cost of requiring greater work to style a page. 

CSS frameworks such as [Blueprint][] and [960 gs][] attempt to correct this, but I've found that these encumber my development process so much that it's actually more work to use one than it is to just write CSS from the ground up. Blueprint, for example, defines font faces, colors, and a huge slew of classes, some of which I might want and some I might not. Even worse, the styles are grouped in a way that seems designed to make finding and modifying or deleting them very difficult. When I've developed with Blueprint, I've spent more time removing extraneous nonsense and reverting its rules than it would take for me to apply a reset and then write my own CSS from the ground up. CSS frameworks require not only more time on my part, they also makes my CSS harder to maintain. 

As a result of these issues, I often find myself using a reset stylesheet and just hand coding all of my CSS from the ground up. This has a few problems:

- I end up repeating a large amount of work from one site to the next to get hum-drum basic styles working, and 
- I tend to forgot to style certain elements (`code`, `abbr`, `del`, sometimes even `blockquote`).

Fed up with this, I decided to create a stylesheet that would first reset browser defaults, and then apply sensible defaults to them. This stylesheet would serve a similar purpose to the user-agent stylesheet provide by a browser, except that it would be consistent across browsers. I had seen [Tripoli][], and found it to be a great project, but had a few disagreements with it:

1. Tripoli disables deprecated HTML elements via CSS. I'm all for standards, but my goal is to apply sensible default styles informed by the principle of least surprise, not try to use a stylesheet as a platform my opinions. 
2. Tripoli also uses browser hacks to achieve greater compatibility with older browsers, which is something I always try to avoid (mostly by not supporting older browsers). 
3. Tripoli applies some of its styles by looking for an element with class `content`. I wanted to avoid making any stipulations about the nature of your markup.



[sr-home]: http://sixrevisions.com/
[reset-intro]: http://sixrevisions.com/css/css-tips/css-tip-1-resetting-your-styles-with-css-reset/
[eric-reset]: http://meyerweb.com/eric/tools/css/reset/
[eric]: http://meyerweb.com/
[blueprint]: http://www.blueprintcss.org/
[960 gs]: http://960.gs/
[Tripoli]: http://devkick.com/lab/tripoli/
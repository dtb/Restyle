A CSS reset is a stylesheet that clears out inconsistent default styles across browsers. This gives us as developers greater control over the final look of our pages, and forces us to define our own styles, rather than lazily relying on inconsistent browser defaults. If you're new to the concept of reset stylesheets, [Six Revisions][1] has a [great introduction][2] to the concept, including some examples of the inconsistencies in cross-browser default styling.

### Consistency, but at what cost?

I've done a lot of work with CSS in recent projects, and I've been pondering CSS resets. I use the popular [reset stylesheet][3] published by [Eric Meyer][4], because it's small and light, and in the public domain. I'm very happy with it as a reset, but I've been struck by one of the drawbacks of CSS resets: CSS resets give us greater consistency, at the cost of requiring greater work to style a page. 

CSS frameworks such as [Blueprint][5] and [960 Grid System][6](960.gs) attempt to correct this, but I've found that these encumber my development process so much that it's actually more work to use one than it is to just write CSS from the ground up. Blueprint, for example, defines font faces, colors, and a whole slew of classes, some of which I might want and some I might not. Even worse, the styles are grouped in a way that seems designed to make finding and modifying or deleting them very difficult; some styles are even defined in multiple places. When I've developed with Blueprint, I've spent more time removing extraneous nonsense and reverting its rules than it would take for me to apply a reset and then write my own CSS from the ground up. 

To be fair, 960.gs has a different aim than Blueprint. 960.gs is a rapid prototyping tool for layouts, and for that purpose, it is excellent. When worked on [Give-a-Weigh][giveaweigh] with [Jeremy Lindblom][jeremy] and [Edgar Hassler][edgar], we only had a single evening to finish it, and 960.gs proved an invaluable tool for rapidly building up the layout. Since it's a *layout* tool, and not a *style* tool, 960.gs defines only [the most basic of styles][960gs-style]. This is appropriate for that tool, but there's still a small gap to fill:

*   Using only a reset stylesheet, or a layout-centric tool like 960.gs I end up repeating a large amount of work from one site to the next to get hum-drum basic styles working, and 
*   I tend to forgot to style certain elements (`code`, `abbr`, `del`, sometimes even `blockquote`).

### Introducing ReStyle

Fed up with this, I decided to create ReStyle: a stylesheet that first **re**sets browser defaults, and then applies sensible default **style**s. This stylesheet serves a similar purpose to the user-agent stylesheet provide by a browser, except that it's consistent across browsers. I had seen [Tripoli][7], and found it to be a great project, but had a few gripes with it:

1.  Tripoli disables deprecated HTML elements via CSS. I'm all for standards, but my goal is to apply sensible default styles informed by the principle of least surprise. I believe there's a good conversation to be had about dropping support for these elements, but I don't believe a stylesheet is the appropriate place to have it.
2.  Tripoli also uses browser hacks to achieve greater compatibility with older browsers, which is not a priority for me. I develop sites for IE7 and above, so I can get away with this. Your mileage may vary if you do not have that luxury.
3.  Tripoli applies some of its styles by looking for an element with class `content`. I wanted to avoid making any stipulations about the nature of your markup, in order to provide sensible defaults everywhere.

#### About ReStyle

[ReStyle][restyle] is available on GitHub, and is placed under the BSD license.

In creating ReStyle, I stuck with the reset stylesheet from Eric Meyer. This stylesheet provides a good starting point, though it does have a few issues in Internet Explorer 7 (e.g., header tags remain bolded, address tags are italicized) due to the browsers poor implementation of the `inherit` value in CSS.

For typography and rhythm, I turned to [A List Apart][ala]. In particular, for setting font sizes in a consistent manner, I used the techniques described (and rigorously tested) in [How to Size Text in CSS][sizetext]. In setting margins, I tried to follow [Setting Type on the Web to a Baseline Grid][vertical-grid], at least in principle, allowing text to follow a vertical grid. I also set the `font-family` of body text to be a sans-serif, simply because I find it to be much more readable and attractive. I also fixed the bizarre quirk of Firefox and Chrome that [causes them to display monospaced fonts much smaller][monospace-fix] than their surrounding text.

Beyond those few, I tried to make uncontroversial decisions. Unordered lists are displayed as bulleted lists, ordered as numbered with arabic numerals, `<strong>` bolds, `<em>` italicizes, and so on. 

I look forward to using ReStyle on future projects, and hope you will do the same. Using Restyle or a similar stylesheet provides all the benefits of using a reset stylesheet, and also provides a good set of default styles that reduces programmer workload. It does so without the cruft and insane design decisions that come along with many CSS frameworks.

 [1]: http://sixrevisions.com/
 [2]: http://sixrevisions.com/css/css-tips/css-tip-1-resetting-your-styles-with-css-reset/
 [3]: http://meyerweb.com/eric/tools/css/reset/
 [4]: http://meyerweb.com/
 [5]: http://www.blueprintcss.org/
 [6]: http://960.gs/
 [7]: http://devkick.com/lab/tripoli/
[giveaweigh]: http://www.giveaweigh.com/
[jeremy]:http://webdevilaz.com/
[edgar]: http://edgarhassler.com/
[960-gs-style]: http://github.com/nathansmith/960-Grid-System/blob/master/code/css/uncompressed/text.css
[restyle]: http://github.com/notjim/restyle
[ala]: http://www.alistapart.com/
[sizetext]: http://www.alistapart.com/articles/howtosizetextincss/
[vertical-grid]: http://www.alistapart.com/articles/settingtypeontheweb/
[monospace-fix]: http://www.undermyhat.org/blog/2009/09/css-font-family-monospace-renders-inconsistently-in-firefox-and-chrome/
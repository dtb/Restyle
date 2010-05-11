# About ReStyle

ReStyle is an attempt to provide a minimal, sensible `base.css`--that is, a stylesheet that first resets inconsistent browser styles, then provides sensible defaults. In creating ReStyle, I used the [reset stylesheet][meyerweb] from Eric Meyer. This stylesheet provides a good starting point, though it does have a few issues in Internet Explorer 7 (e.g., header tags remain bolded, address tags are italicized) due to the browser's poor implementation of the `inherit` value in CSS. You may see a demo at [my website][demo].

For typography and rhythm, I turned to [A List Apart][12]. In particular, for setting font sizes in a consistent manner, I used the techniques described (and rigorously tested) in [How to Size Text in CSS][13]. In setting margins, I tried to follow [Setting Type on the Web to a Baseline Grid][14], at least in principle, aligning text to a vertical grid. I also set the `font-family` of body text to be a sans-serif, simply because I find it to be much more readable and attractive. I also [fixed the bizarre quirk][15] of Firefox and Chrome that causes them to display monospaced fonts much smaller than their surrounding text.

Beyond those few, I tried to make uncontroversial decisions. Unordered lists are displayed as bulleted lists, ordered as numbered with arabic numerals, `<strong>` bolds, `<em>` italicizes, and so on. 

ReStyle is available under the BSD License. For more information about my motivations in the development of ReStyle, see [the blog post][16].

[meyerweb]: http://meyerweb.com/eric/tools/css/reset/
[12]: http://www.alistapart.com/
[13]: http://www.alistapart.com/articles/howtosizetextincss/
[14]: http://www.alistapart.com/articles/settingtypeontheweb/
[15]: http://www.undermyhat.org/blog/2009/09/css-font-family-monospace-renders-inconsistently-in-firefox-and-chrome/
[16]: 
[demo]: http://davidthomasbernal.com/wp-content/uploads/2010/05/demo.html
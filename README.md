# Footnotes Popover

JavaScript to present HTML footnotes as a popover. Optional CSS included.

It looks like this:

<div style="text-align:center;">
<a href="http://www.flickr.com/photos/mattgemmell/8720959368/" title="Footnote popover by Matt Gemmell, on Flickr"><img src="http://farm8.staticflickr.com/7432/8720959368_ecaffb8e46_o.png" width="526" height="132" alt="Footnote popover" style="border:2px solid #ccc;"></a>
</div>


## Authors

Original [footnotes script by Lukas Mathis](http://ignorethecode.net/blog/2010/04/20/footnotes/) ([@ignorethecode](https://twitter.com/ignorethecode)).

Modifications by [Matt Gemmell](http://mattgemmell.com/) ([@mattgemmell](http://twitter.com/mattgemmell)).


## License

Public Domain, by Lukas' request.

If you prefer, or if your jurisdiction does not recognise the concept of a Public Domain license, you may choose to use this script under a BSD license. Or MIT, or Apache, or whatever you like. Even GPL, if you _really_ must.


## Requirements

* [jQuery](http://jquery.com)


## Compatibility

I've tested it on the latest versions (as of 8th May 2013) of:

- Safari, Chrome and Firefox on OS X.
- Safari on iPad and iPhone.

I'm quite motivated to keep it working on those browsers.

I've also been told by others that it works on:

- Internet Explorer 10 on Windows.
- Internet Explorer on Windows Phone 7.5.
- Chrome on iOS.

I am _substantially less motivated_ to keep it working on those, or others I haven't mentioned. But feel free to check/implement such support yourself.


## Installation

Load the JavaScript in your webpage, probably in the HEAD section, like this:

	<script src='/javascripts/footnotes.js' type="text/javascript"></script>

Make sure jQuery is loaded too. You might also want to use the CSS file in this project, or at least paste its contents into your own stylesheet.


## Installation - Octopress

If you're using [Octopress](http://octopress.org), you already have jQuery, so don't worry about that. To install the script, simply:

1. Copy the `footnotes.js` file to `source/javascripts/`
2. Add the aforementioned line of code to `source/_includes/custom/head.html`
3. (Add the CSS wherever you prefer, if you want it.)
4. Regenerate and deploy your site.


## Making footnotes

This works with the fairly standard ["Markdown Extra" footnotes syntax](http://michelf.ca/projects/php-markdown/extra/#footnotes) (Markdown itself doesn't support footnotes as-is). The latest versions of various Markdown processors like [rdiscount](https://github.com/davidfstr/rdiscount) and [kramdown](http://kramdown.rubyforge.org) support the syntax just fine.

If you're using Octopress, the latest version as of 7th May 2013 also supports the syntax (here's [how to update your Octopress installation](http://octopress.org/docs/updating/)).

This is an example of how to make footnotes:

	My name is Matt Gemmell [^1]
	
	[^1]: Two Ms and two Ls.

(Note the colon ":" after the footnote definition; it's easy to forget.)

The thing after the caret "^" symbol doesn't have to be a number; most alphanumeric strings work just fine. You can put the footnote definition anywhere you want in your document (I like to define them after the paragraph in which they're used), and your Markdown processor will almost certainly collect them all at the bottom of the output.

A linked superscript number will be placed in the output where your used the footnote (it'll always be a number, even if you used something else). Clicking it will jump to the footnote definition at the end of your document. Definitions also have a return link immediately afterwards, to send the user back up to where the footnote was referenced from.


## Footnote popovers

So far, so good - all of the above footnotes functionality is courtesy of your Markdown processor, not this JavaScript.

This JavaScript adds something extra: when the user hovers over one of those superscript number-links that reference a footnote, they'll see a popover with the contents of the footnote, so they don't need to actually move away from that part of the page. The popover will be dismissed when the user moves their mouse out of the reference link (or out of the popover itself).

On touch-screen devices, where hovering isn't really possible, the first tap on the link will show the popover, and the second tap will jump to the footnote definition at the bottom of the page. The popover will also have a close/X button (only on touch devices), as shown below on a Retina iPhone in landscape mode:

<div style="text-align:center;">
<a href="http://www.flickr.com/photos/mattgemmell/8719851479/" title="Footnotes popover on iPhone by Matt Gemmell, on Flickr"><img src="http://farm8.staticflickr.com/7414/8719851479_ce9a8ca7bf.jpg" width="500" height="136" alt="Footnotes popover on iPhone"></a>
</div>

Popovers will be sized sensibly (and will be capped to the user's screen, when on a mobile device), and their content will scroll if necessary. They will be positioned immediately adjacent to the reference link which spawns them, whenever possible.

The back-links from the actual footnote definitions at the bottom of the page will not be shown in the popovers (where possible), since you're already at that part of the page, and it wouldn't make much sense to have a redundant link.


## Support

There is absolutely no support available. Feel free to report issues on the [github issue tracker for this project](https://github.com/mattgemmell/footnotes-popover/issues), or indeed to fix them yourself and submit a pull request!


## Don't overuse footnotes

Footnotes are best when used judiciously. There's a time and a place for them, but they _do_ momentarily distract the reader from the flow of your piece. This JavaScript helps with that to some extent, but it's not a panacea.

Despite the context, I managed to write this entire Read Me without using a single one. I trust that you'll exercise similar restraint.


## A closing note

I'm an iOS/Mac developer, and I don't do much web stuff. JavaScript isn't really one of my regular languages, so do forgive any awfulness. Or make it better, and tell me why mine (or Lukas', I suppose) is rubbish. I do have [lots of Objective-C open source stuff](http://mattgemmell.com/source/) that's guaranteed to be fab. Some of it is probably on your iOS device or Mac right now, actually.

Footnotes are best for medium to long-form writing, like the kind you just aren't doing enough of on your blog lately. How long has it been since you posted something substantial? _That_ long? Similar for me. Perhaps we both ought to make more time for writing this year.

As ever, enjoy the code.

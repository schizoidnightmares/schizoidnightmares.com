---
title: Website redesign
description: I finally got around to redesigning my website from the ground up
last_modified_at: September 26, 2023
---

I finally got around to redesigning my website from the ground up.

**UPDATE 2023-08-01: I have updated my website since this post. Some details may be out of date.**

I designed my previous website using the drag-and-drop online editor <a href="https://weebly.com/" target="_blank">Weebly ⧉</a>, with customized CSS.[^1] After experimenting with different drag-and-drop tools (attracted to their ease of use), I settled on <a href="https://jekyllrb.com/" target="_blank">Jekyll ⧉</a> instead. My goal with the redesign is minimalism and user-friendliness. Since Jekyll provides me greater control than Weebly, it serves this goal well.

Jekyll is not a drag-and-drop tool, but it supports Liquid, a template language by Shopify. Jekyll and Liquid allow me to build websites without "repeating myself" too much. Otherwise, managing a website with more than a dozen pages would be very tedious. Right now, of course, this website is quite small as of the time of this post. However, I have provided a good base for the future, and I will build upon what I have developed here.

My website redesign should be responsive on your device, but you're welcome to <a href="https://tally.so/r/mOaDRp" target="_blank">send me any complaints or suggestions ⧉</a>. Unlike my website's previous version, my redesign does not support comments, so you'll have to use the external form provided to contact me. Alternatively, you could contact me on [one of my profiles](/about#profiles) or post on the <a href="https://www.reddit.com/r/SchizoidNightmares/" target="_blank">subreddit ⧉</a>.

## Colour scheme and technicalities
I exclusively use a dark theme for my website and prefer it if possible for all my branding. For choosing the right colour scheme, I utilized Google's <a href="https://m3.material.io/" target="_blank">Material Design 3 ⧉</a>, their <a href="https://www.figma.com/community/plugin/1034969338659738588/Material-Theme-Builder" target="_blank">Material Theme Builder ⧉</a> on Figma in particular.

<div class="table" markdown=0>
    <table style="font-family: monospace">
        <tr><td>{% include color.html color="#eff1f1" %} #eff1f1 — Neutral-Variant95</td></tr>
        <tr><td>{% include color.html color="#e1e3e3" %} #e1e3e3 — Neutral-Variant90</td></tr>
        <tr><td>{% include color.html color="#c4c7c7" %} #c4c7c7 — Neutral-Variant80</td></tr>
        <tr><td>{% include color.html color="#a9acac" %} #a9acac — Neutral-Variant70</td></tr>
        <tr><td>{% include color.html color="#8e9192" %} #8e9192 — Neutral-Variant60</td></tr>
        <tr><td>{% include color.html color="#747878" %} #747878 — Neutral-Variant50</td></tr>
        <tr><td>{% include color.html color="#5c5f5f" %} #5c5f5f — Neutral-Variant40</td></tr>
        <tr><td>{% include color.html color="#2e3132" %} #2e3132 — Neutral-Variant20</td></tr>
        <tr><td>{% include color.html color="#191c1d" %} #191c1d — Neutral-Variant10</td></tr>
    </table>
</div>

As of the time of this post, I only use Neutral-Variant colours. If you select the colour scheme table's text (click and drag), you may notice that all colours except for Neutral-Variant50 have a highlighted background. That is because the highlighted background (appears as ```::selection``` in HTML)[^2] is the same colour as Neutral-Variant50. Highlighted (i.e. selected) text itself appears as Neutral-Variant90.

You may also notice that the website hyphenates text for a cleaner appearance. This feature uses the ```hyphens``` property in CSS. However, sometimes it's necessary to avoid hyphenating terms using this feature, such as to improve text comprehension. Unfortunately, CSS does not support automatically treating manually inserted hyphens (e.g. in the technical term "Neutral-Variant50") as non-breaking. I have to manually wrap hyphenated terms that I don't want to be auto-hyphenated in an HTML span[^3] using the ```white-space``` property, with a ```nowrap``` value.

Users on W3C's CSS Working Group Editor Drafts GitHub repository <a href="https://github.com/w3c/csswg-drafts/issues/3434" target="_blank">brought up this issue ⧉</a> and workarounds in late 2018. We will not likely see official support for a fix in the foreseeable future. I considered creating a Jekyll plugin, but I am unfamiliar with Ruby (the programming language Jekyll plugins use). Building a plugin is much more complicated than using HTML spans.

### Larger screen sizes and accessibility
I don't use a large screen in development, so it is possible that my website may not appear right on larger dimensions, especially since I limit the content area to 700 pixels in width. Please let me know if you use a large screen and find this is the case.

Another concern is accessibility, particularly for users with poor eyesight and non-English readers. I cannot do much about the latter since English is the only language I can write fluently. In any case, I will consider accessibility on a user-demand and case-by-case basis.

## Finishing thoughts
The source code ("software") for my website, as listed in [licensing](/terms#licensing), is available for others to use under the MIT License. I plan to release my website development files later on GitHub as a reference for others. They can potentially use that to generate a similar-looking website with Jekyll.

[^1]: CSS stands for Cascading Style Sheets.
[^2]: HTML stands for HyperText Markup Language.
[^3]: A span is an HTML tag that I can use in combination with CSS to style part of a text.
# HTML Tags by Content and Function

A practical guide to HTML elements grouped by the kind of content or behavior they provide. Some elements fit more than one category; they are listed where they are commonly used.

## Text

Elements for paragraphs, headings, inline meaning, and text structure:

- `<h1>`-`<h6>` - headings
- `<p>` - paragraph
- `<span>` - generic inline container
- `<div>` - generic block container
- `<br>` - line break
- `<hr>` - thematic break
- `<strong>`, `<b>` - importance, or stylistic bold
- `<em>`, `<i>` - emphasis, or stylistic offset
- `<mark>` - highlighted text
- `<small>` - side comments or small print
- `<del>`, `<ins>` - deleted and inserted text
- `<sub>`, `<sup>` - subscript and superscript
- `<blockquote>`, `<q>` - block and inline quotations
- `<pre>`, `<code>`, `<kbd>`, `<samp>`, `<var>` - code and computer-related text
- `<abbr>`, `<cite>`, `<dfn>`, `<time>`, `<data>` - annotated text and machine-readable values
- `<address>` - contact information
- `<ul>`, `<ol>`, `<li>`, `<dl>`, `<dt>`, `<dd>` - lists

```html
<h1>Main title</h1>
<h2>Section</h2>
<h3>Subsection</h3>
<h4>Small heading</h4>
<h5>Smaller heading</h5>
<h6>Smallest heading</h6>
<p>A paragraph with a <span>span</span> and a line break<br>here.</p>
<hr>
<p><strong>Important</strong>, <b>bold</b>, <em>emphasized</em>, and <i>offset</i> text.</p>
<p><mark>Highlighted</mark> <small>small print</small>, <del>removed</del>, <ins>added</ins>, H<sub>2</sub>O, and x<sup>2</sup>.</p>
<blockquote>A longer quotation.</blockquote>
<p>She said, <q>Hello.</q></p>
<pre><code>print("Hello")</code></pre>
<p>Press <kbd>Ctrl</kbd>+<kbd>S</kbd>; output: <samp>Saved</samp>; variable: <var>count</var>.</p>
<p><abbr title="HyperText Markup Language">HTML</abbr> article by <cite>A. Author</cite>; <dfn>markup</dfn> is structured text.</p>
<p>Published <time datetime="2026-09-28">September 28</time>; item <data value="SKU-42">blue mug</data>.</p>
<address>Contact: <a href="mailto:hello@example.com">hello@example.com</a></address>
<ul><li>Unordered item</li></ul>
<ol><li>Ordered item</li></ol>
<dl><dt>HTML</dt><dd>A markup language</dd></dl>
<div>A generic block container</div>
```

## Images

- `<img>` - embed an image
- `<picture>` - choose among responsive image sources
- `<source>` - provide an image source inside `<picture>` (also used by audio and video)
- `<figure>`, `<figcaption>` - self-contained media or illustration with a caption

```html
<figure>
	<picture>
		<source srcset="large.webp" media="(min-width: 800px)">
		<img src="small.jpg" alt="A mountain at sunrise">
	</picture>
	<figcaption>Sunrise in the mountains</figcaption>
</figure>
```

## Audio

- `<audio>` - embed audio, optionally with browser controls
- `<source>` - provide alternative audio files or formats inside `<audio>`
- `<track>` - timed text such as captions or subtitles for media

```html
<audio controls>
	<source src="interview.mp3" type="audio/mpeg">
	<track kind="captions" src="interview-captions.vtt" srclang="en" label="English">
	Your browser does not support audio.
</audio>
```

## Video

- `<video>` - embed video, optionally with browser controls
- `<source>` - provide alternative video files or formats inside `<video>`
- `<track>` - captions, subtitles, chapters, or descriptions for media
- `<iframe>` - embed a video player hosted by another site

```html
<video controls poster="preview.jpg">
	<source src="lesson.mp4" type="video/mp4">
	<track kind="captions" src="lesson-en.vtt" srclang="en" label="English">
</video>
<iframe src="https://www.youtube.com/embed/VIDEO_ID" title="Video player" allowfullscreen></iframe>
```

## Files and Downloads

- `<a href="..." download>` - link to a file and suggest downloading it
- `<input type="file">` - let a user choose a file to upload
- `<label>` - provide an accessible name for a file input
- `<form>` - submit selected files when configured for file upload
- `<object>` - embed an external resource, such as a PDF, when supported
- `<embed>` - embed external content; support depends on the browser and resource

File upload forms commonly need `method="post"` and `enctype="multipart/form-data"`. These are attributes, not HTML tags.

```html
<form action="/upload" method="post" enctype="multipart/form-data">
	<label for="document">Choose a document:</label>
	<input id="document" name="document" type="file">
	<button type="submit">Upload</button>
</form>
<a href="guide.pdf" download>Download the guide</a>
<object data="guide.pdf" type="application/pdf" width="400" height="300">Open the PDF</object>
<embed src="guide.pdf" type="application/pdf" width="400" height="300">
```

## Links and Navigation

- `<a>` - link to a page, location, email address, or downloadable file
- `<nav>` - group important navigation links
- `<link>` - connect the document to an external resource, commonly a stylesheet or icon; it is not a clickable page link
- `<area>` - clickable region inside an image map; typically contains an `href`

```html
<head>
	<link rel="stylesheet" href="styles.css">
</head>
<nav aria-label="Main navigation">
	<a href="/">Home</a>
	<a href="/about">About</a>
</nav>
```

## Image Maps

- `<map>` - define a client-side image map
- `<area>` - define a clickable region within that map
- `<img usemap="#map-name">` - associate an image with a `<map>`

Image maps are for clickable regions over an image. Interactive geographic maps are usually built with a mapping library or embedded with `<iframe>`; there is no dedicated built-in HTML map element for them.

```html
<img src="plan.png" alt="Room plan" usemap="#rooms">
<map name="rooms">
	<area shape="rect" coords="10,10,120,90" href="/rooms/kitchen" alt="Kitchen">
</map>
```

## Graphs and Data Visualizations

HTML provides containers, while the drawing is typically done with SVG, Canvas, or a JavaScript charting library:

- `<svg>` - scalable vector graphics; suitable for charts and diagrams
- `<canvas>` - scriptable drawing surface; suitable for dynamic charts
- `<figure>`, `<figcaption>` - wrap a visualization and its caption
- `<table>`, `<caption>`, `<thead>`, `<tbody>`, `<tfoot>`, `<tr>`, `<th>`, `<td>` - present chart data in an accessible tabular form
- `<progress>` - show completion progress
- `<meter>` - show a value within a known range

`<svg>` and `<canvas>` are elements; chart types such as bar graphs and pie charts are not HTML tags.

```html
<figure>
	<svg role="img" aria-label="A simple bar chart" viewBox="0 0 120 80">
		<rect x="10" y="40" width="20" height="30" fill="steelblue"></rect>
		<rect x="45" y="20" width="20" height="50" fill="steelblue"></rect>
		<rect x="80" y="5" width="20" height="65" fill="steelblue"></rect>
	</svg>
	<figcaption>Values increase from left to right.</figcaption>
</figure>
<canvas id="chart" width="240" height="120">Chart data: 3, 5, 7</canvas>
<table>
	<caption>Example values</caption>
	<thead><tr><th scope="col">Month</th><th scope="col">Sales</th></tr></thead>
	<tbody><tr><td>January</td><td>12</td></tr></tbody>
	<tfoot><tr><th scope="row">Total</th><td>12</td></tr></tfoot>
</table>
<label for="upload-progress">Upload progress:</label>
<progress id="upload-progress" value="60" max="100">60%</progress>
<label for="disk-usage">Disk usage:</label>
<meter id="disk-usage" value="0.7">70%</meter>
```

## Animations

There is no general-purpose HTML animation element. Animation is usually provided by CSS, JavaScript, or SVG:

- `<svg>` - can contain SVG animation elements such as `<animate>`, `<animateTransform>`, and `<set>`
- `<canvas>` - can be animated by drawing frames with JavaScript
- `<video>` - can play a pre-rendered animation
- `<marquee>` - obsolete; avoid using it for animation

CSS animation uses properties and `@keyframes` in a stylesheet, not HTML tags.

```html
<svg viewBox="0 0 100 30" role="img" aria-label="A moving circle">
	<circle cx="10" cy="15" r="5">
		<animate attributeName="cx" from="10" to="90" dur="2s" repeatCount="indefinite"></animate>
		<animateTransform attributeName="transform" type="rotate" from="0 50 15" to="360 50 15" dur="2s" repeatCount="indefinite"></animateTransform>
		<set attributeName="fill" to="tomato" begin="1s"></set>
	</circle>
</svg>
<canvas id="animation" width="100" height="30">Animated content</canvas>
<video controls src="animation.mp4">Your browser does not support video.</video>
<!-- Obsolete example only; do not use <marquee> in new pages. -->
<marquee>Old scrolling text</marquee>
```

## Quick Reference

| Category | Common elements |
| --- | --- |
| Text | `<p>`, `<h1>`-`<h6>`, `<span>`, `<strong>`, `<em>` |
| Images | `<img>`, `<picture>`, `<figure>`, `<figcaption>` |
| Audio | `<audio>`, `<source>`, `<track>` |
| Video | `<video>`, `<source>`, `<track>`, `<iframe>` |
| Files | `<input type="file">`, `<a download>`, `<object>` |
| Links | `<a>`, `<nav>`, `<link>`, `<area>` |
| Image maps | `<map>`, `<area>`, `<img usemap>` |
| Graphs | `<svg>`, `<canvas>`, `<table>`, `<progress>`, `<meter>` |
| Animations | `<svg>`, `<animate>`, `<animateTransform>`, `<canvas>`, `<video>` |
---
title: "How to use distill"
date: 27-11-2017
layout: distill
---

This is step-by-step guide line on how to use distill template. After this article, you should be quite familiar about the main features of distill template. In most of the time, you don't need to do any CSS hacks. This template is meant to abstract all of that. We got you covered. For the interactive visualization, we highly encourage you to try and learn basic [D3.js](https://www.d3js.org). D3.js indeed might seem quite overwhelming at first, however, there are tons of examples that you can easily modify on. If you cannot do that at all, fear not. We are expecting that. We _can_ help here, too. The problem is, it is just quite hard to explain to our team what do you want your visualization to be look like. If you can handle that, I think we can help you. Note that, however, we are _not_ paid to do this task. We _will_ try to help you as much as we can.

## Philosophy

We want to separate the document content from the document appearance. Pretty much like [LaTeX](https://www.latex-project.org/about). Having said that, we using something instead of LaTeX. The only difference, however, is we will be using HMTL instead of PDF, for our publications.

We could have used LaTeX as our markup language. But that would have possessed more difficulties for both us and our authors: since we are using HTML anyway, why not stick with that?

## Write your first document

We are using [distill template](https://distill.pub) to render your submissions. Distill is a machine learning journal that is dedicated to clear explanations in machine learning.

Any document has a metadata; authors, their affiliations, date, title, etc. Let us start with that.

```html
<dt-code>
<script>
title: "Getting Started with Distill"
authors:
  - Mohamed Yousif: https://adonese.github.io
  - Mohamed Jaafar: https://wadjaafar.github.io
  affilations:
    - Gndi: https://gndi-sd.com
    - Gndi: https://gndi-sd.com
</script>
</dt-code>
```

<dt-code block language="python">
def myfunc(i, x):
    "This function does something cool."
    return i **x
</dt-code>
To try that out, create a new file called it `<your_submission_title>.html`, the name doesn't matter much, however, the extension should be `*.html`. And copy paste this to it.

```html
<dt-code>
<!doctype html>
<meta charset="utf-8">
<script src="https://distill.pub/template.v1.js"></script>

<script>
title: "Getting Started with Distill"
authors:
  - Mohamed Yousif: https://adonese.github.io
  - Mohamed Jaafar: https://wadjaafar.github.io
  affilations:
    - Gndi: https://gndi-sd.com
    - Gndi: https://gndi-sd.com
</script>
</dt-code>
```

The first and the second line are just HTML tags. The third line, however, is our distill template. It is this magic line that makes everything works. Save this file and use your browser to open that file ^[1]. But that's clearly not everything you can do in a paper. A paper typically has an abstract, multiple levels of sections, acknowledgments, and bibliography.

```html
<dt-code>
(...)
<dt-article>
<h1>Using Distill template</h1> <!-- Your first section, usually introduction -->
<p>Paragraphs can be written using <p> tag.</p>
<h2>Subsection</h2>
<p>Extra contents...</p>
</dt-article>
</dt-code>
```
I assume by now you get the idea of nesting levels. The number in `<h*>` indicates the level of nesting--`<h1>` is the highest. We can also `cite`, using
```html
<dt-code>
(...)
<dt-article>
<p>You can cite external sources using <dt-cite key="id"></dt-cite>.</p>
</dt-article>

<!-- you need to add the bibitem like this -->

<script type="text/biblography">
@article{<id>,
title: {Your publication title},
author: {Name(s)},
journal: {Journal name},
year: {Date},
url: {it is very important to include a url link for the cited publication.}}
</script>
</dt-code>
```
Acknowledgments and appendixes are included using `<dt-acknowledge>` tag.

```html
<dt-code>
<script type="text/acknowledge">
<p>This is a place to people and organizations that supported your work. 
It is also good to acknowledge software and libraries that make your work possible e.g., MATLAB, Python, etc.</p>
<p>We highly encourage you to include each author's contributions in the acknowledgment part.</p>
</script>

</dt-code>
```
Code snippest and LaTeX are also supported.

```html
<dt-code>
<dt-article>
<dt-code block language="python">
print("Hello World!")
</dt-code>
<p>You can also use inline code snippest by removing `block` fro `dt-code` tag.</p>

<dt-code language="python">print("Hello World")</dt-code>.
</dt-article>
<dt-code>
```

For the LaTeX part, you need to use MathJax. You can use it out of the box. 



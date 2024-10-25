---
layout: post
title: "RMarkdown cheat sheet"
date: 2024-10-25
Categories: R Markdown
permalink: /:title
---

A basic YAML header to start with.
Choose the desired output format.

<pre>
---
title: "RMarkdown Example"
author: "Mohammad Ali Nilforooshan"
date: "6 August 2017"
output: html_document
# output: pdf_document
# output: word_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
</pre>

horizontal rule `***` or `---`

---

### Formatting

Manual line break: End the line with two or more spaces.

*italic* `*italic*` and _italic_ `_italic_`

**bold** `**bold**` and __bold__ `__bold__`

superscript<sup>2</sup> `superscript^2^`

subscript<sub>2</sub> `subscript~2~`

~~strikethrough~~ `~~strikethrough~~`

[link](http://rmarkdown.rstudio.com) `[link](http://rmarkdown.rstudio.com)`

<http://rmarkdown.rstudio.com> `<http://rmarkdown.rstudio.com>`

# Header 1 `# Header 1`

## Header 2 `## Header 2`

### Header 3 `### Header 1`

> block quote `> block quote`

endash: – `--`

emdash: — `---`

ellipsis: ... `...`

<span style="color:red">Roses are red.</span> `<span style="color:red">Roses are red.</span>`

### Equations (LaTeX)

inline $equation$ `inline $equation$`

Display equation `$$ equation $$` $$ equation $$

### Insert Image

image: ![](https://www.rstudio.com/wp-content/uploads/2016/09/RStudio-Logo-Blue-Gray-125.png)

`image: ![](https://www.rstudio.com/wp-content/uploads/2016/09/RStudio-Logo-Blue-Gray-125.png)`

Inserting a resized and centered image in the document:

<pre>
```
{r, out.width = "120px", echo=FALSE, fig.align='center'}
knitr::include_graphics("imsage.png")
```
</pre>

### Lists

* unordered list
* item 2
    + sub-item 1
    + sub-item 2

```
* unordered list  
* item 2  
    + sub-item 1  
    + sub-item 2  
```

1. ordered list
2. item 2
     + sub-item 1
     + sub-item 2

```
1. ordered list
2. item 2
     + sub-item 1
     + sub-item 2
```

### Tables

Table Header  | Second Header
------------- | -------------
Table Cell    | Cell2
Cell 3        | Cell4

```
Table Header  | Second Header
------------- | -------------
Table Cell    | Cell2
Cell 3        | Cell4
```

### Codes

This `plain code` is written inline.

<pre> This `plain code` is written inline. </pre>

<pre>
```
This is a plain code block.
```
</pre>

Evaluate the code inline.

```
There were `r nrow(cars)` cars studied.
```

Show and evaluate the code.

<pre>
```{r cars}
summary(cars)
```
</pre>

Show the code, but do not evaluate it.

<pre>
```{r eval=FALSE}
print("Don't run me")
```
</pre>

Embed  a plot.

<pre>
```{r pressure, echo=FALSE}
plot(pressure)
```
</pre>

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.

### display options

option | default | effect
------ |-------- | ------
eval | TRUE | Whether to evaluate the code and include its results
echo | TRUE | Whether to display code along with its results
warning | TRUE | Whether to display warnings
error | FALSE | Whether to display errors
message | TRUE | Whether to display messages
tidy | FALSE | Whether to reformat code in a tidy way when displaying it
results | "markup" | "markup", "asis", "hold", or "hide"
cache | FALSE | Whether to cache results for future renders
comment | "##" | Comment character to preface results with
fig.width | 7 | Width in inches for plots created in chunk
fig.height | 7 | Height in inches for plots created in chunk

For more details visit <http://yihui.name/knitr/>

***

### Centred text - PDF output only

```
\begin{center}
centred text
\end{center}
```

```
\newline
```

```
\hfill
```

***

### Table of contents

```
---
title: "Sample Document"
output:
  html_document:
    toc: true
    theme: united
---
```

It can be custmized further, such as `toc_depth`.

If you want to have the table of contents in a new page, drop `toc` and use some latex language.

```
---
title: "Title"
author: "Name"
output: pdf_document
---

\newpage # adds new page after title
\tableofcontents # adds table of contents
\listoffigures
\listoftables
\newpage
```


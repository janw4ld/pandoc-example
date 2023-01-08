---
title: Pandoc Markdown Example
subtitle: A document to demonstrate pandoc markdown usage
author: [janw4ld, Jane Doe]
bibliography: example.bib
geometry: a4paper,margin=2.5cm
csl: https://raw.githubusercontent.com/citation-style-language/styles/master/ieee.csl
header-includes: |
   \usepackage{graphicx}
   \usepackage{wrapfig}
   \usepackage{multicol}
---

\newpage

# Introduction
This document is supposed to be read with the source and render side-by-side;
It demonstrates some of the pandoc markdown+latex syntax, which can be learned
by observing the code in the md source, and its resulting output in the PDF.

# This is a heading
The headings appear as sections in the table of content. If your pdf viewer
supports document outlines, the headings will also  appear there. The table of
contents is automatically generated from the headings by Pandoc. You can
generate it in VSCode or write it manually instead if you want to.

## This is a heading 2

## This heading is hidden from the table of contents {.unnumbered .unlisted}

### heading 3
Headings > 3 are inlined into paragraphs

#### heading 4
Like this

##### heading 5
And this too,   
but \LaTeX doesn't like headings 5 and 6

###### heading 6 looks
 like regular text

# The basics
## Paragraphs
This is a paragraph.   

markdown text can have *italics*, **bold**, `monospace` and  ~~strikethrough~~ 
in it. \uline{underlined text isn't a thing in markdown}, but u can do it in 
\LaTeX, and in <u>HTML</u> too, \LaTeX has \uuline{dunderline text} as well.

Pure markdown doesn't support ^superscript^ and ~subscript~, but pandoc does.

This is a new paragraph, separated from the previous by two newlines.  
To have a line break in a paragraph, you need to end the line
before it with two or three spaces.

## Lists
1. This is a list
1. It numbers itself
1. automagically

- unnumbered 
- lists
- are a thing
- too

## Tables
| this | is     | a table |
| ---- | ------ | ------- |
| the  | first  | row     |
| the  | second | one     |

You can float the table to the right or left using \LaTeX's float environment.


## Citations
BibTex references can be added in pandoc, and Zotero references can be saved as
BibTex. [@hasselquistQUICThroughputFairness2022]

Citation styles are defined in Citation Style Language (CSL) files, this is the
same format used by Zotero and Mendeley Cite, you can just copy your old style
as is.

# References[^1] [^2] {.unnumbered .unlisted}

::: {#refs}
:::

[^1]: Inserting refs is optional, if you don't insert them in the doc, pandoc adds them to the last page.
[^2]: This is a footnote, btw.


## Links
Links can be added as follows [this is a link to google](https://google.com), 
you can also link to other sections in the paper using the heading's id, which
is usually the heading's text all lowercase with `-` instead of spaces, if you
have duplicate heading names the IDs will be suffixed with `-1`, `-2`, etc.  

Example:   
[this is a link to the heading 2](#this-is-a-heading-2).

# This is a heading {.unnumbered .unlisted}
[This is a link to this heading](#this-is-a-heading-1)   
Heading links can also be copied from the table of contents, or the markdown
preview.

## Images
Images can be inserted in markdown like this:   
![md logo](resources/auto-20230108110032.png)  
but this feels so out of control, right?   

\newpage

Using \LaTeX, images can be scaled and positioned in the document.

\begin{figure}
   \centering  % centering the image (obviously) optional.
   \includegraphics[width=0.3\linewidth]{./resources/auto-20230108110032.png}
\end{figure}
  
<!--
![https://ctan.org/lion/files/ctan_lion_2400.png](https://ctan.org/lion/files/ctan_lion_2400.png)
-->

\begin{wrapfigure}{r}{0.3\textwidth}
   \begin{center}
      \includegraphics[width=0.28\textwidth]{./resources/auto-20230108111244.png}
      \caption{This lion is the TeX mascot}
      \label{fig:lion}
   \end{center}
\end{wrapfigure}

Here is a bunch of text that we can put around an image. The image will be shown
on the right side of the paper, but our text can go all around it. There will be
spacing above and below the image where text can go.  This spacing can actually 
be controlled by using a negative value with `vskip`, but we will not be going
into that here. It will be just our little secret: you, me, and the compiler. I
hope this is enough dummy text for this example.  If not, I will have to type up
some more. Oops, I just tried compiling it.  Apparently I need to include a bit
more.  I could go on a bit and tell you more secrets of image placement.  Did 
you know that you can use the `center` environment around the `includeimage` to
make things look even prettier?  It's true.  The control which \LaTeX provides
with it is nice.

Figures are automatically numbered and can be referenced in the text using their
label. These references are also links to their figures.   
Example: Figure (\ref{fig:lion}) is TeX's picture.

## Footnotes
Footnotes[^4] are a thing.[^3] They are numbered and ordered automatically, but
numbering them by hand is possible.[^note]

[^3]: This is a footnote.
[^4]: pandoc & github support footnotes, but not pure markdown.
[^note]: This is an automatic footnote, created and referenced by id. This is
the recommended method of footnote creation.

## Multicolumns
\begin{multicols}{2}
Lorem ipsum dolor sit amet consectetur adipisicing elit. Eveniet ut 
doloribus ducimus laudantium odit, nostrum consequuntur fugit cumque 
vitae officia a possimus corrupti repellendus numquam voluptatibus illo!
Fuga, explicabo veritatis! Lorem ipsum dolor, sit amet consectetur
adipisicing elit. Soluta cumque facilis consequuntur tenetur veniam 
eveniet distinctio neque maxime fugiat assumenda. Odio placeat quod 
iusto illum. Odit, tenetur voluptate. Sapiente, soluta?
\end{multicols}

## Codeblocks
This is a formatted c++ code block:
```cpp
int main() {
    std::cout << "Hello, world!" << std::endl;
    return 0;
}
```

A lot of other languages are supported, as well as console output, and even
\LaTeX code.
```console
$ echo "Hello, world!"
Hello, world!
```

## Blockquotes
> This is a blockquote.
> It can span multiple lines,   
> and has the same rules as a paragraph.

## Tasklists
   - [ ] are a thing
   - [ ] but only in
   - [x] github &
   - [x] pandoc md


# Version Control??
Yep! You can use git to version control your markdown files, and vscode has a 
built-in git interface. You can also use github to host your markdown files, 
kinda as a backup and a way to share them with others. This paragraph is in a
new commit from the previous one. Every commit is a point in the project's time 
that you decided to save and assign a name to. You can always go back to any
commit, so you should create a commit for every significant addition or change 
to your project. Git can be used to collaborate with others, but that's a bit 
complicated for a text editing workflow.

It's not recommended to have your rendered documents in git, because they are 
binary files that will make your repo grow uncontrollably with every change.

# AI-assisted text editing
You can use your university email address or your student ID card to get a free
github pro subscription that allows u to use GitHub Copilot in VSCode. GitHub 
copilot suggests predictions of what you're going to type, and you can ask it
questions in the document or the comments. It can help with git commands, md and
\LaTeX syntax or even answer general trivia.

To ask a question you need to precede it with "q:" or copilot might not suggest
a response to it.   
Here's an example:

- q: Who is the queen of England?
- a: Elizabeth II

# Further Reading
- [Pandoc Markdown](https://pandoc.org/MANUAL.html#pandocs-markdown)   
  [https://pandoc.org/MANUAL.html#pandocs-markdown](https://pandoc.org/MANUAL.html#pandocs-markdown)
- [Overleaf \LaTeX](https://www.overleaf.com/learn)   
  [https://www.overleaf.com/learn](https://www.overleaf.com/learn)
<!-- 
# A dirty hack you might need
If you want a table with a vertical header, you can write it in html, but pandoc
will not render it in the pdf.
<table><tr><th>   
   This is a
   </th><td>   
    It's not a thing
   </th><td>   
   but this is
</td></tr><tr><th>   
   vertical headered
   </th><td>   
   you should wanna
   </th><td>   
   how you
   </td></tr><tr><th>   
   HTML table
   </th><td>   
   use in a document
   </th><td>   
   can do it
</td></tr></table>
-->
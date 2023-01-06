---
title: Pandoc Markdown Example
bibliography: example.bib
---

\newpage
# This is a heading
The headings appear as sections in the table of content. If your pdf viewer supports document outlines, the headings will also appear there. The table of contents is automatically generated from the headings by Pandoc. You can generate it in VSCode or write it manually instead if you want to.

## This is a heading 2
This is a paragraph.   

markdown text can have *italics*, **bold**, `monospace` and ~~strikethrough~~ in it. \uline{underlined text isn't a thing in markdown}, but u can do it in LaTex, and in <u>HTML</u> too, LaTex has \uuline{dunderline text} as well.

This is a new paragraph, separated from the previous by two newlines.   
In order to have a line break in a paragraph, you need to end the line before it with two or three spaces.

BibTex references can be added in pandoc, and zotero references can be saved as BibTex. [@hasselquistQUICThroughputFairness2022]

## This heading is hidden from the table of contents {.unnumbered .unlisted}
1. This is a list
1. It numbers itself
1. automagically

| this | is | a table |
|------|----|---------|
| the  | first  | row |
| the  | second | one |

- unnumbered 
- lists
- are a thing
- too

<!-- 
tasklists
- [ ] are
- [x] a thing
- [ ] but only
- [ ] in github
-->

### heading 3
Headings > 3 are inlined into paragraphs

#### heading 4
Like this

##### heading 5
And this too,   
but LateX doesn't like headings 5 and 6

###### heading 6 looks like regular text, btw

# Version Control??
Yep! You can use git to version control your markdown files, and vscode has a built in git interface. You can also use github to host your markdown files, kinda as a backup and a way to share them with others.

\newpage

# References[^1] [^2]
::: {#refs}
:::

[^1]: Inserting citations is optional, if you don't insert them in the doc pandoc adds them to the last page.
[^2]: This is a footnote, btw.

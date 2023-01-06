---
title: Pandoc Markdown Example
bibliography: example.bib
csl: https://raw.githubusercontent.com/citation-style-language/styles/master/ieee.csl
---

\newpage

# This is a heading
The headings appear as sections in the table of content. If 
your pdf viewer supports document outlines, the headings will also 
appear there. The table of contents is automatically generated 
from the headings by Pandoc. You can generate it in VSCode or
write it manually instead if you want to.


## This is a heading 2
This is a paragraph.   

markdown text can have *italics*, **bold**, `monospace` and 
~~strikethrough~~ in it. \uline{underlined text isn't a thing
in markdown}, but u can do it in LaTex, and in <u>HTML</u> 
too, LaTex has \uuline{dunderline text} as well.

This is a new paragraph, separated from the previous by two newlines.
To have a line break in a paragraph, you need to end the line
before it with two or three spaces.

BibTex references can be added in pandoc, and zotero references
can be saved as BibTex. [@hasselquistQUICThroughputFairness2022]


This is a formatted c++ code block:
```cpp
int main() {
    std::cout << "Hello, world!" << std::endl;
    return 0;
}
```

A lot of other languages are supported, as well as console
output, and even LaTeX code.
```console
$ echo "Hello, world!"
Hello, world!
```

> This is a blockquote.
> It can span multiple lines,   
> and has the same rules as a paragraph.


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
Yep! You can use git to version control your markdown files, and vscode has a built-in git interface. You can also use github to host your markdown files, kinda as a backup and a way to share them with others. This paragraph is in a new commit from the previous one. Every commit is a point in the project's time that you decided to save and assign a name to. You can always go back to any commit, so you should create a commit for every significant addition or change to your project. Git can be used to collaborate with others, but that's a bit complicated for a text editing workflow.

# AI-assisted text editing
You can use your university email address or your student ID card to get a free github pro subscription that allows u to use GitHub Copilot in VSCode.
GitHub copilot suggests predictions of what you're going to type, and you can ask it questions in the document or the comments. It can help with git commands, md and latex syntax or even answer general trivia.

To ask a question you need to precede it with "q:" or copilot might not suggest a response to it.   
Here's an example:

   - q: Who is the queen of England?
   - a: Elizabeth II

<!-- 
# Dirty hacks you might need
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

\newpage

# References[^1] [^2]

::: {#refs}
:::

[^1]: Inserting refs is optional, if you don't insert them in the doc, pandoc adds them to the last page.
[^2]: This is a footnote, btw.

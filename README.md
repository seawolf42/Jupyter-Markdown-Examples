# Jupyter Markdown

Highlights:

* [Getting Started](#getting-started)
* [Markdown Overview](#overview)
* [Jupyter Extensions for Markdown](#jupyter-specific)
* [All the Rest](#other)
* [Notes](#notes)
* [Resources](#resources)


## <a name="getting-started"></a>Getting Started

Install the 'jupyter' package:

    pip install jupyter

Open a notebook in jupyter:

    jupyter notebook


## <a name="overview"></a>Markdown Overview

The basic idea is that Markdown is a *very simple* markup language that captures the essence of your document structure in a human-readable form. There is a direct translation from the constructs in your text file to the HTML that will be generated to display it.

The most common syntax elements:

### Text

Just type on a line. One or more empty lines between non-empty lines demarks paragraphs.

### Headings

Start the line with one to six `#` characters to turn that line into a heading; one is the biggest, six is the smallest.

### Emphasis

Use a single `*` character before and after the text you want italicized: `*hi*` becomes *hi*.

Use two consecutive `*` characters before and after the text you want boldfaced: `**pow**` becomes **pow**.

### Bulleted lists

Start the line with a `*` or a `-` character to make the line a bullet item.

Indent the line with two spaces before the `*` to make a sub-item in the list.

The following:

    * this is the main-item
      * this is the sub item
    * this is the next main item

... becomes:

* this is the main-item
  * this is the sub item
* this is the next main item

### Numbered lists

Same as bulleted, but start the line with `1.`.

Indent the same way: precede the line with two spaces to make a sub-item (`__1.` becomes 1.a... those underlines represent spaces).

Numbers don't matter, the actual numbers will be calculated when the list is rendered. I just use `1.` for each item in the list.

The following:

    1. this is the main-item
    1. this is the next main item

... becomes:

1. this is the main-item
1. this is the next main item

You can have bullets inside a numbered list:

    1. this is the main item
      * this is a bullet under the main item
    1. this is the next main item

... becomes:

1. this is the main item
  * this is a bullet under the main item
1. this is the next main item

### Links

Wrap the text you want linked with `[` and `]`, and immediately follow it with the URL wrapped in `(` and `)`.

For example, the following markdown `[Google](http://google.com)` will turn into this link: [Google](http://google.com).

### Codeblocks

Code can be represented inline or stand-alone.

**Inline:** For a small number of words inline, wrap them in `` ` `` characters: `` `print 'hello world'` `` turns into this: `print 'hello world'` (note that it's just part of the paragraph).

**Stand-alone:** To show several consecutive lines of code, just start each line with four or more spaces; the first four spaces indicate it is part of the block and the remainder are used for furtner indentation in your code.

    for i in x:
        print 'i:', i

### Horizontal rules

Just put three or more hyphens, asterisks, or underlines on a line by themselves, such as `---`.

### Tables

To create a table, just draw the table boundaries using `|` and `-` characters. For example:

    | This | is    |
    |------|-------|
    |   a  | table |

... becomes:

| This | is    |
|------|-------|
|   a  | table |

**Note:** The table boundaries don't have to be aligned (just make sure your horizontal dividers are at least 3 characters long). You could get the same effect as above by using:

    | This | is |
    |------|---|
    | a |table         |

### Inline HTML

You can insert HTML anywhere in your Markdown and it will be passed through as-is to the renderer. For instance, `<strong>pow</strong>` becomes <strong>pow</strong>.


## <a name="jupyter-specific"></a>Jupyter Extensions for Markdown

*Jupyter*'s engine allows you to embed some non-standard Markdown syntax.:

### LaTeX expressions

You can embed LaTeX equations both inline and as stand-alone text.

**Inline:** To embed inline, surround the LaTeX expression with `$` characters. For example, `$e^{i\pi} + 1 = 0$` becomes <math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>e</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mi>π</mi></mrow></msup><mo>+</mo><mn>1</mn><mo>=</mo><mn>0</mn></math>.

**Stand-alone:** Expressions can also be moved to a line by themselves by wrapping them in `$$` characters (two `$` characters at each end of the expression) and placing them on a line by themselves. For example:

    $$e^x=\sum_{i=0}^\infty \frac{1}{i!}x^i$$

... becomes:

<math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><msup><mi>e</mi><mi>x</mi></msup><mo>=</mo><munderover><mo>∑</mo><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>=</mo><mn>0</mn></mrow><mi mathvariant="normal">∞</mi></munderover><mfrac><mn>1</mn><mrow><mi>i</mi><mo>!</mo></mrow></mfrac><msup><mi>x</mi><mi>i</mi></msup></math>

### File references

You can include references to local files to be rendered as images or otherwise served via your Markdown document:

    <img src="../images/python_logo.svg" />

## <a name="other"></a>All the Rest

See the resources for more detail on each of these and the more complicated structures you might want to create.

## <a name="notes"></a>Notes

* R Markdown does not support smileys. You'll have to handle those in a different way. :)

## <a name="resources"></a>Resources

* [Markdown Reference](http://daringfireball.net/projects/markdown/syntax)
* [Markdown Syntax Guide (SourceForge)](https://sourceforge.net/p/jupiter/wiki/markdown_syntax/)
* [Markdown Cells (jupyter-notebook.readthedocs.io)](http://jupyter-notebook.readthedocs.io/en/latest/examples/Notebook/Working%20With%20Markdown%20Cells.html)

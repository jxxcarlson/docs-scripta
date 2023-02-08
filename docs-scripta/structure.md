# Document Structure

## MicroLaTeX

A MicroLaTeX document starts with title line
and a tag line.  The tag line has the form
`\tags{tag1, tag2, ...}`.  The first tag is
obligatory and has the form 
`USERNAME:Unique-identifier`.  The identifier
is generated automatically from the title.

```text
\title{Notes on Entropy}

\tags{jxxcarlson:notes-on-entropy}
```

Here is a slightly larger example:

```text
\title{Notes on Entropy}

\tags{jxxcarlson:notes-on-entropy, shannon}

\contents

\section{Entropy in physics}

A single spin has states $U$ and $D$ (up and down). 
An $N$-spin system s a sequence of $N$ spins, e.g.,

$$
UUDUDD
$$

Suppose that there are $N_U$ spins in
state $U$ and $N_D$ in state $D$.  We call
$(N_U, N_D)$ a \emph{macrostate} of the system.
A macrostate generally consists many \emph{microstates}, e.g.,

\begin{code}
UUUDDD
UUDUDD
UDUUDD
DUUUDD
...
DDDUUU
\end{code}

for the macrostate $(3,3)$.  If $s$ is a macrostate,
let $\Omega(s)$ be the number of microstates belonging
to it.  Then

\begin{definition}
The entropy of the macrostate $s$ is $\log\Omega(s)$.
\end{defintion}

...

\section{Shannon Entropy}
```

The structure of this larger example will be familiar
to LaTeX users.  Nonetheless, there are some 
differences of syntax and features:

- MicroLaTeX is *block-structured*.  Blocks must have
a blank line above and below.  Displayed mathematical
text is a block, where the double dollar signs occupy
lines of their own.  Any `\begin .. \end` pair is
also a block.

- The `\contents` macro automatially generates the 
table of contents, provided that there are at least two
sections.

- Note that the `\tags` macro in this case defines an
additional tag, `shannon`.  Such tags are useful in 
searches.  A search on `shannon` will retrieve this
document.

**NOTE.** On export, MicroLaTeX is translated to standard LaTeX.

## L0



```text
| title
Notes on Entropy

[tags jxxcarlson:notes-on-entropy]
```

Below is a longer example. L0 is also block-structured,
where blocks consist of contiguous  *non-empty* lines
bounded above and below by a blank line.  There are
four kinds of blocks:

- Paragraphs
- Ordinary blocks
- Verbatim blocks
- Special blocks

An ordinary block is a header of the form `| NAME`
followed by its body.  The `title` and `contents`
blocks are ordinary. A verbatim block has a header
of the form `|| NAME`.  The `code` block is a verbatim
block, as are the `equation` and `aligned` blocks, corresponding to the
LaTeX `equation` and `align` blocks.  A block
which starts with the single line `$$` as in the 
example below, correponds to the `$$ ... $$` construct
in LaTeX. It is a special block.

```text
| title
Notes on Entropy

[tags jxxcarlson:notes-on-entropy, shannon]

| contents

| section
Entropy in physics

A single spin has states $U$ and $D$ (up and down). 
An $N$-spin system s a sequence of $N$ spins, e.g.,

$$
UUDUDD


Suppose that there are $N_U$ spins in
state $U$ and $N_D$ in state $D$.  We call
$(N_U, N_D)$ a [emph macrostate] of the system.
A macrostate generally consists many [emph microstates], e.g.,

|| code
UUUDDD
UUDUDD
UDUUDD
DUUUDD
...
DDDUUU


for the macrostate $(3,3)$.  If $s$ is a macrostate,
let $\Omega(s)$ be the number of microstates belonging
to it.  Then

| definition
The entropy of the macrostate $s$ is $\log\Omega(s)$.

...

| section
Shannon Entropy

```

As with LaTeX, one has `section`, `subsection`,
and `subsubsection` blocks.  One can also say
`| section 1`, `| section 2`, etc.

**NOTE.** On export, L0 is translated to standard LaTeX.


## XMarkdown

The minimal structure of an XMarkdown document 
is similar to that of an L0 document.  The rest
of the text can be normal Markdown, or can be
XMarkdown, i.e., Markdown + some extensions.

```text
| title
Notes on Entropy

@[tags jxxcarlson:notes-on-entropy]
```

Below is a longer XMarkdown documents.  



```text
| title
Notes on Entropy

@[tags jxxcarlson:xmarkdown-test, shannonx]

| contents

# Entropy in physics

A single spin has states $U$ and $D$ (up and down). 
An $N$-spin system is a sequence of $N$ spins, e.g.,

$$
UUDUDD
$$

Suppose that there are $N_U$ spins in
state $U$ and $N_D$ in state $D$.  We call
$(N_U, N_D)$ a *macrostate* of the system.
A macrostate generally consists many @[emph microstates], e.g.,

|| code
UUUDDD
UUDUDD
UDUUDD
DUUUDD
...
DDDUUU


for the macrostate $(3,3)$.  If $s$ is a macrostate,
let $\Omega(s)$ be the number of microstates belonging
to it.  Then

| definition
The entropy of the macrostate $s$ is $\log\Omega(s)$.

...

# Shannon Entropy
```

In an XMarkdown document, you can use most of standard
Markdown, e.g., sections and subsections
with `#`, `##`, etc., backticks for inline
code, triple backticks for blocks of code,
`*italic text*` `**bold text**`, and dashes
for bullet lists.  For numbered lists, we
use a leading dot:

```text
. Bread

. Wine

. Cheese
```

Note that you can freely "borrow" L0 syntax in 
XMarkdown, e.g, displayed mathematical text, the
definition and code blocks, etc.


**NOTE.** On export, XMarkdown is translated to standard LaTeX.

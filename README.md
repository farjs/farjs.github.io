
[![CI](https://github.com/farjs/farjs.github.io/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/farjs/farjs.github.io/actions/workflows/ci.yml?query=workflow%3Aci+branch%3Amain)

## FAR.js GitHub Pages

### Jekyll Theme

The site is built using the [jekyll-theme-slate](https://github.com/pages-themes/slate) theme.

### Previewing the site locally

If you'd like to preview the site locally (for example, in the process of proposing a change):

1. Clone down the site's repository (`git clone https://github.com/farjs/farjs.github.io`)
2. `cd` into the site's directory
3. Run `./script/bootstrap.sh` to install the necessary dependencies
4. Run `./script/server.sh` to start the preview server
5. Visit [`localhost:4000`](http://localhost:4000) in your browser to preview the site

### Running tests

The site contains a minimal test suite, to ensure a site with the theme would build successfully.
To run the tests, simply run `./script/cibuild.sh`.
You'll need to run `./script/bootstrap.sh` one before the test script will work.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### How to embed draw.io Diagrams

[GitHub support](https://github.com/jgraph/drawio-github) is now available https://www.draw.io/?mode=github

An example for integration into GitHub wikis is available here [Embed Diagrams](https://github.com/jgraph/drawio/wiki/Embed-Diagrams)

Example diagrams are available [here](https://github.com/jgraph/drawio-diagrams)

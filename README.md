# Ubiquitous Couscous
> A repo which shows how you can get AppVeyor Server to automatically build PDF documentation from Markdown files (using pandoc).

[![Build Status][ci-image]][ci-url]

This is an AppVeyor Server (on-premise AppVeyor solution) pipeline for automatically generating PDF documents from markdown files.

What this does is, it generates a single PDF file for each folder found. 
Each folder should then, in turn, contain the markdown files you want to put into the PDF.
Since this uses globbing, if you want a certain markdown file to appear before another, you should make sure it appears alphabetically before.
For example, `1.Somethimg.md` will appear in the PDF before `2.Something else.pdf`.

## Installation

It is highly recommended to install AppVeyor Server on a Linux server.
I haven't tested this workflow on a Windows installation nor, do I intend to (for one, I don't have a Windows server).


Anyways, once you have the AppVeyor Server installed you just have to install LaTex and Pandoc.

```sh
sudo apt install pandoc texlive-full
```

If you know what you're doing, you can install the specific parts of LaTex to save some space.

## Contributing

1. Fork it (<https://github.com/yourname/yourproject/fork>)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'feat: add some fooBar'`)
   1. Make sure to conform to [Conventional Commits Standard.][commit-convention]
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request

<!-- Markdown link & img dfn's -->
[ci-image]: https://ci.tgrhavoc.me/api/projects/status/u3xpt2fd95db6ypx
[ci-url]: https://ci.tgrhavoc.me/project/AppVeyor/ubiquitous-couscous
[commit-convention]: https://www.conventionalcommits.org/en/v1.0.0-beta.4/
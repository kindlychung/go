# The Go Programming Language

Go is an open source programming language that makes it easy to build simple,
reliable, and efficient software.

## Modifications

* Created a `yywarnl` function
* Changed all `yyerrorl` to `yywarnl` when there is `declared but not used` error

## Build 

* _Make sure you have a recent version of go already installed_ (you need go to build itself)
  * If you installed go by your system package manager or brew, you are all set
  * If your previous installation of go is done from source, you need to keep the old repo as your bootstrap root. For example, if you have a repo `~/goProjects/go` in which you have built your previous version of go, you need to `cp -av ~/goProjects/go ~/goProjects/go_old && export GOROOT_BOOTSTRAP=~/goProjects/go_old`
* If you haven't cloned the go repo yet, do it: `cd ~/goProjects && hub clone go`
* If you already have the repo cloned, switch to the 1.16 release branch: `git switch release-branch-allow-unused.go1.16`
* Now you can build go with your old version of go: `cd src && ./make.bash`

## Update and rebuild

* Make sure you have the upstream set up properly:
```bash
git remote -v
origin  https://github.com/kindlychung/go.git (fetch)
origin  https://github.com/kindlychung/go.git (push)
upstream        https://github.com/golang/go.git (fetch)
upstream        https://github.com/golang/go.git (push)
```

* Bring in the upstream changes

```bash
git fetch upstream
git rebase upstream/release-branch.go1.16 # and then fix any conflicts
git push --force origin release-branch.go1.16
```

* Now you can build the new version of go: `cd src && ./make.bash`


![Gopher image](https://golang.org/doc/gopher/fiveyears.jpg)
*Gopher image by [Renee French][rf], licensed under [Creative Commons 3.0 Attributions license][cc3-by].*

Our canonical Git repository is located at https://go.googlesource.com/go.
There is a mirror of the repository at https://github.com/golang/go.

Unless otherwise noted, the Go source files are distributed under the
BSD-style license found in the LICENSE file.

### Download and Install

#### Binary Distributions

Official binary distributions are available at https://golang.org/dl/.

After downloading a binary release, visit https://golang.org/doc/install
for installation instructions.

#### Install From Source

If a binary distribution is not available for your combination of
operating system and architecture, visit
https://golang.org/doc/install/source
for source installation instructions.

### Contributing

Go is the work of thousands of contributors. We appreciate your help!

To contribute, please read the contribution guidelines at https://golang.org/doc/contribute.html.

Note that the Go project uses the issue tracker for bug reports and
proposals only. See https://golang.org/wiki/Questions for a list of
places to ask questions about the Go language.

[rf]: https://reneefrench.blogspot.com/
[cc3-by]: https://creativecommons.org/licenses/by/3.0/

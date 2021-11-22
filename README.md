# test-l3build-doc-images
How to supply images to documents unpacked by l3build?

I have a module that I want to manage with l3build.  Unpacking a docstrip file
generates a tex file.  `l3build doc` typesets that generated tex file.  But I
can't figure out how to configure `build.lua` to enable that process to see any
images that should be included.

## reproducing the issue

Command:

    l3build doc foo

* `duck.png` is copied into `docdir`
* `foo.dtx` is typeset in `docdir` (I think?)
* result: success

Command:

    l3build doc bar

* `bar.tex` is unpacked into `unpackdir`
* `tex` is run on `bar.tex` in `unpackdir`
* result: failure because `duck.png` is not found.


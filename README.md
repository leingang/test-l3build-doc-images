# test-l3build-doc-images
How to supply images to documents unpacked by l3build?

## Status

[Fixed in l3build](https://github.com/latex3/l3build/issues/210).  Thanks @josephwright and @zauguin!

## Original synopsis

I have a module that I want to manage with l3build.  Unpacking a docstrip file
generates a tex file.  `l3build doc` typesets that generated tex file.  But I
can't figure out how to configure `build.lua` to enable that process to see any
images that should be included.

## Reproducing the issue

Command:

    l3build doc foo

* `duck.png` is copied into `typesetdir`
* `foo.dtx` is typeset in `typesetdir` (I think?)
* result: success

Command:

    l3build doc bar

* `bar.tex` is unpacked into `unpackdir`
* `tex` is run on `bar.tex` in `unpackdir`
* result: failure because `duck.png` is not found.


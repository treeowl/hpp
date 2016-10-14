`hpp` is a Haskell pre-processor that is also a C90-compatible
pre-processor (with the addition of a `--cpp` flag). It is
packaged as both a library and an executable.

To use as a Haskell preprocessor for resolving `#ifdef` conditionals
and macro expansion, an invocation might look like,

```
hpp -DDEBUG Foo.hs
```

To use as a C preprocessor, an invocation might look like,

```
hpp -DDEBUG --cpp foo.c
```

To have GHC use `hpp` as the C pre-processor, add this line to the top
of a Haskell source file that makes use of the `CPP` `LANGUAGE`
pragma,

```
{-# OPTIONS_GHC -cpp -pgmPhpp #-}
```

Or add this line to your `.cabal` file:

```
ghc-options: -pgmPhpp
```

Note that you will need to ensure that the `hpp` executable is available in your build environment (e.g. you can add `hpp` as a `build-depends` in your `.cabal` file).

# 🌷 Tulip as a Racket `#lang`

This is a Racket implementation of the [Tulip][tulip] programming language. It implements Tulip as a Racket `#lang`. This is an extreme work-in-progress, so the language support is currently somewhat poor (and Tulip itself is still a work in progress, itself).

To install, clone this repository, then run `raco pkg install --link path/to/tulip-lib`. You should then be able to write Tulip programs simply by writing `#lang tulip` at the top of your modules.

```tulip
#lang tulip

decr = [ x => subtract x 1 ]

test = {
  is-even = [ 0 => .t; decr x > is-odd  ]
  is-odd  = [ 0 => .f; decr x > is-even ]
  [ .even x => is-even x; .odd x => is-odd x ]
}

test (.even 3)
test (.odd  3)
```

[tulip]: https://github.com/tulip-lang/tulip
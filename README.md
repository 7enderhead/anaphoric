[![Build Status,](https://img.shields.io/travis/jsmaniac/anaphoric/master.svg)](https://travis-ci.org/jsmaniac/anaphoric)
[![Coverage Status,](https://img.shields.io/codecov/c/github/jsmaniac/anaphoric/master.svg)](https://codecov.io/gh/jsmaniac/anaphoric)
[![Build Stats,](https://img.shields.io/badge/build-stats-blue.svg)](http://jsmaniac.github.io/travis-stats/#jsmaniac/anaphoric)
[![Online Documentation,](https://img.shields.io/badge/docs-online-blue.svg)](http://docs.racket-lang.org/anaphoric/)
[![License: CC0 v1.0.](https://img.shields.io/badge/license-CC0-blue.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

anaphoric
=========

Anaphoric conditional forms for `racket`:

```
(aif (member 'a lst)
  (displayln it)
  (displayln "not found")) ;; Can't use "it" in the else clause.

(awhen (member 'a lst)
  (displayln it))

(acond
  [(member 'a lst) (displayln it)]
  [(member 'b lst) (displayln it)]
  [else (displayln "not found")]) ;; Can't use "it" in the else clause.
```

This package also provides hygienic versions:

```
(if-let [x (member 'a lst)]
  (displayln x)
  (displayln "not found")) ;; Can't use "x" in the else clause.

(when-let [x (member 'a lst)]
  (displayln it))

(cond-let x
  [(member 'a lst) (displayln x)]
  [(member 'b lst) (displayln x)]
  [else (displayln "not found")]) ;; Can't use "x" in the else clause.
```

Installation
------------

```
raco pkg install --deps search-auto anaphoric
```

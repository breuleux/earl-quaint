
earl-quaint
===========

This packages defines the `Q` macro which allows the embedding of
[Quaint](https://breuleux.github.io/quaint)
markup in
[Earl Grey](http://earl-grey.io).

```earlgrey
require-macros:
   earl-quaint ->
      Q

Q"Hello __everyone!"         ;; => % {"Hello", strong % "everyone"}
```

The result is an `ENode`, the same data structure that the `%`
operator returns in Earl Grey. An `ENode` can be converted to HTML:

```earlgrey
require-macros:
   earl-quaint ->
      Q

require: /html

html(Q"Hello __everyone!")   ;; => "Hello <strong>everyone</strong>"
```

Alternatively, you can specify a format to convert to directly:

```earlgrey
require-macros:
   earl-quaint ->
      Q(format = "html")

Q"Hello __everyone!"         ;; => % "Hello <strong>everyone</strong>"
```

Earl Grey expressions can be interpolated inside `{}`s.

```earlgrey
favorites = {
   animal = "zebra"
   food = "poutine"
}

Q"My favorite animal is the {favorites.animal}"
```

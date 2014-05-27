# cpath-clj

__cpath-clj__ is a small library to transparently collect files on the classpath based on a
given base directory. Since that directory might be located inside a JAR this is not always
trivial.

[![endorse](https://api.coderwall.com/xsc/endorsecount.png)](https://coderwall.com/xsc)

## Usage

__Leiningen ([via Clojars](https://clojars.org/cpath-clj))__

```clojure
[cpath-clj "0.1.0"]
```

__REPL__

```clojure
(require '[cpath-clj.core :as cp])

(cp/resources "static")
;; => {"/js/main.js" [#<URI file:/.../static/js/main.js>]
;;     "/js/lib.js"  [#<URI jar:file:/...!/static/js/lib.js>]}
```

`cpath-clj.core.resources` finds all locations on the classpath with the path `static`,
then collects the URIs of all resources residing under those locations.

## License

Copyright &copy; 2014 Yannick Scherer

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.

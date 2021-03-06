# boot-expectations

[Boot] task for running [Expectations] tests

[](dependency)
```clojure
[seancorfield/boot-expectations "1.0.3"] ;; latest release
```
[](/dependency)

## Usage

Add `boot-expectations` to your `build.boot` dependencies and `require` the
namespace:

```clj
(set-env! :dependencies '[[seancorfield/boot-expectations "X.Y.Z" :scope "test"]])
(require '[seancorfield.boot-expectations :refer :all])
```

If your tests are in a directory that is not included in the classpath, you will need to add it

```
(set-env! :source-paths #{"test"})
```

You will need to do this _outside_ the middleware layer of any prior task since `boot-expectations` creates a pod based on the dependencies outside its middleware layer for efficiency.

You can see the options available on the command line:

```bash
$ boot expectations -h
```

or in the REPL:

```clj
boot.user=> (doc expectations)
```

## Continuous Testing

Whisper some magic incantations to boot, and it will run tests every time you save a file
```
boot watch expectations
```
with sound!
```
boot watch speak expectations
```

## Changes

1.0.3 - 12/25/2015 - Add `--requires` / `--shutdown` options.
1.0.2 - 12/24/2015 - Create pod before task body for efficiency.
1.0.1 - 12/20/2015 - Add `distinct` to dedupe list of namespaces (#7).
1.0.0 - 12/19/2015 - Initial public release.

## License

Copyright © 2015 Sean Corfield

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.

[1]: http://clojars.org/seancorfield/boot-expectations/latest-version.svg?cache=5
[2]: http://clojars.org/seancorfield/boot-expectations
[Boot]: https://github.com/boot-clj/boot
[Expectations]: https://github.com/jaycfields/expectations

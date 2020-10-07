# swahili-dsl
![Version](https://img.shields.io/badge/version-0.1.0-blue.svg?cacheSeconds=2592000)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Travis CI](https://travis-ci.com/collinsmuriuki/swahili-dsl.svg?branch=master)]("https://travis-ci.com/collinsmuriuki/swahili-dsl)

> An attempt of creating a DSL. A DSL is a mini "language" embedded in a Rust macro. Will continue to expand on it as I build on my declarative macro knowledge.
>
> Heavily influenced by [swahili-lang](https://github.com/malcolmkiano/swahili) and [macro-lisp](https://github.com/JunSuzukiJapan/macro-lisp)

## Examples

```rs
// declaring variables
swh!(wacha jina = 2020);

// booleans
swh!(wacha swala = swh!(kweli));
swh!(wacha swala = swh!(uwongo));

// list comprehensions
swh!(matokeo; kwa n katika 0..=10 => kama n%2 == 0);

// inbuilt functions
let l = swh!(urefu(vec![1,2,4]));
swh!(andika("Habari Duinia"));

// collections
swh!(wacha l = swh!(orodha -> [1,2,4]));
swh!(wacha hm = swh!(kamusi -> 
            "id" => "#12",
            "jina" => "Juma"
        ));

// arithmetic operations
swh!(wacha hesabu = swh!(suluhisha 4 * 4));
swh!(wacha hesabu = swh!(suluhisha (12/4) * (16/4)));

// ternary operator
swh!(wacha swala = swh!(kweli));
swh!(swala => swh!(andika("Kweli")) ; swh!(andika("Uwongo")));
```

## Run tests

```sh
cargo test
```

This project is [MIT](LICENSE) licensed.

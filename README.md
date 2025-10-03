# catdoc-parser

## note to self

* download `catdoc-0.95.tar.gz` from [www.wagner.pp.ru](https://www.wagner.pp.ru/~vitus/software/catdoc/)  
* [github](https://github.com/petewarden/catdoc) clone fails to configure
* run `configure`
* find `src/config.h`

> [!TIP]
> in `catdoc/src/Makefile`
> ```
> -sFILESYSTEM=0 -sNO_FILESYSTEM=1
> ```

```
cd catdoc/src
make catdoc-wasm
```

fails because `emsdk` in `third_party` is not good 

# catdoc-parser

## note to self

* download `catdoc-0.95.tar.gz` from [www.wagner.pp.ru](https://www.wagner.pp.ru/~vitus/software/catdoc/)  
* [github](https://github.com/petewarden/catdoc) clone fails to configure
* run `configure`

```
catdoc.c:8:10: fatal error: 'config.h' file not found
    8 | #include <config.h>
      |          ^~~~~~~~~~
```

```
./catdoc.h:11:10: fatal error: 'config.h' file not found
   11 | #include <config.h>
      |          ^~~~~~~~~~
```

> [!WARNING]
> maybe `-DHAVE_CONFIG_H` is unnecessary?


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

> [!WARNING]
> 
> ```
> cd catdoc/src
> make catdoc-wasm
> ```
> fails because `emsdk` in `third_party` is not good 

just install normally

```
cd ~
git clone https://github.com/emscripten-core/emsdk.git
cd emsdk
./emsdk install latest
./emsdk activate latest
source ./emsdk_env.sh
```

```
~/emsdk/upstream/emscripten/emcc \
 -o ../../catdoc.wasm \
		catdoc.c reader.c writer.c \
		analyze.c rtfread.c charsets.c \
		substmap.c fileutil.c confutil.c \
		numutils.c ole.c \
		-I. -O3 -DHAVE_CONFIG_H \
		-DCATDOC_VERSION=\"0.95\" \
		-DCHARSETPATH=\"charsets\" \
		-sEXPORTED_FUNCTIONS=_get_text,_get_author,_get_last_author,_get_version,_get_title,_get_subject,_get_keywords,_get_comments,_get_annotation_authors\
		-sSTANDALONE_WASM -sWARN_ON_UNDEFINED_SYMBOLS=0 \
		--no-entry -sFILESYSTEM=0 -sNO_FILESYSTEM=1 -sALLOW_MEMORY_GROWTH -sMAXIMUM_MEMORY=1GB
```

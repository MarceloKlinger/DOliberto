# DOliberto

o diário oficial do século XXI.

## directory contents

```

- doli/ :: backend source
  |
  - server.py ::
  |    this simple server accepts POST requests with .json data (in the
  |    appropriate doliberto format), produces a .pdf using xelatex, and
  |    returns it for download. it currently saves the .json in a 
  |    google cloud server.
  |
  - latex/ :: 
    |
    - doli.py :: 
    |     main script, consumes the .json input, treats it, and calls 
    |     pylatex to produce .pdf output.
    |
    - doliberto.cls :: 
        a LaTeX class for typesetting a Diário Oficial (D.O., public 
        gazette). it is meant to typeset Mesquita's D.O., but (I hope)
        is flexible enough to handle other government units, as along 
        as their styles are similar.

        it requires XeLaTeX to compile, as we like UTF-8 and native font
        support by default. (it can probably be compiled with LuaTeX 
        too, but we haven't tried that yet).

- Dockerfile :: 
    packages all of the above + doliberto's dependencies: a texlive 
    subset needed to run XeLaTeX, flask, Apache, all in a Debian image.

```

## documentation

documentation is in the source files.

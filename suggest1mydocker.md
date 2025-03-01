# suggest : "MyDockerTool" to make dockerfile by using local files.

## making pure this only mit<auther=me> allow

MyONBUILD/Dockerfile
```dockerfile
ENV MOB /myonbuild/
ENV MOBUILDER $MOB/buildscript/
RUN mkdir $MOB $MOBUILDER
ONBUILD RUN $MOBUILDER/env
ONBUILD CMD $MOBUILDER/init
ONBUILD ENTRYPOINT $MOB/shell
```

MyONBUILD/MOB_WORKDIR/Dockerfile
```dockerfile
ONBUILD WORKDIR $MOB_WORKDIR
```

MyONBUILD/MOB_USER/Dockerfile
```dockerfile
ONBUILD USER $MOB_USER
```

# === [ prj info (introduce) ] === #

python + cython + cffi : deployment
(c/c++) + XS(perl) : main part
awk + sed + ed + grep : core app

# === [ fto ] === #

SubLexedToken.dtd
```dtd
<!ENTITY S &#32;>
<!ENTITY T &#09;>
<!ENTITY L &#10;>
<!ENTITY C &#59;>
```

ReLexedToken.dtd
```dtd
<!ENTITY K &#91;>
<!ENTITY ꓘ &#93;>
```

Symbols.dtd
```
<!ENTITY %RE "https://faraway6834.github.io/~/">
<!ENTITY %DT "xedToken.dtd">
<!ENTITY %LE "Le&%DT;">
<!ENTITY %EL "&%RE;Re&%LE;">
<!ENTITY %SL "&%RE;Sub&%LE;">
<!ENTITY %EP "&%RE;EnbfPa&%DT;">
<!ENTITY S SYSTEM &%SL;>
<!ENTITY T SYSTEM &%SL;>
<!ENTITY L SYSTEM &%SL;>
<!ENTITY C SYSTEM &%SL;>
<!ENTITY K SYSTEM &%EL;>
<!ENTITY ꓘ SYSTEM &%EL;>
```

EbnfParxedToken.dtd
```dtd
<!ENTITY %SY "https://faraway6834.github.io/~/Symbols.dtd">
<!ENTITY S SYSTEM &%SY;>
<!ENTITY T SYSTEM &%SY;>
<!ENTITY L SYSTEM &%SY;>
<!ENTITY C SYSTEM &%SY;>
<!ENTITY K SYSTEM &%EY;>
<!ENTITY ꓘ SYSTEM &%EY;>
<!ELEMENT k CDATA>
<!ELEMENT v CDATA?>
<!ELEMENT c CDATA>
<!ELEMENT w (&S;|&T;|&S;)*>
```

fto.dtd
```dtd
<!ENTITY %EP SYSTEM "https://faraway6834.github.io/~/Symbols.dtd">
<!ENTITY S SYSTEM &%SY;>
<!ENTITY T SYSTEM &%SY;>
<!ENTITY L SYSTEM &%SY;>
<!ENTITY C SYSTEM &%SY;>
<!ENTITY K SYSTEM &%EY;>
<!ENTITY ꓘ SYSTEM &%EY;>
<!DOCTYPE k SYSTEM &%EP;>
<!DOCTYPE v SYSTEM &%EP;>
<!DOCTYPE c SYSTEM &%EP;>
<!DOCTYPE w SYSTEM &%EP;>
<!ELEMENT fto (x|kv|c)*>
<!ELEMENT kv (x|k|v|c)*>
<!ELEMENT x CDATA?>
```

fto.ebnf
```ebnf
<B64C> := (0|...|9)|(A|...|Z)|(-|_)
<B64E> := {<B64C>}3
<B64LEXED_UNICODE> := {<B64E>}
<swhitespace> := &(S|T);
<newline> := &L;
<mwhitespace> := <swhitespace>|<newline>
<core> := {(<B64LEXED_UNICODE>|<swhitespace>)}
<comment> := &C;<core><newline>
<value> := <B64LEXED_UNICODE><core><B64LEXED_UNICODE>
<etcx> := <mwhitespace>
<valuepart> := {<comment>}{<mwhitespace>}<value>{<mwhitespace>}{<comment>}
<etcx> := <mwhitespace>
<key> := &K;<value>&ꓘ;
<kv> := <key>{<valuepart>}
fto := {(<kv>|<comment>|<etcx>)}
```

and some regexes....

# === [ directory.rem ] === #
 - AUTHER.md
 - README.md
remcv.py (algorithm inf)
```python 
from os import chdir as _cd
from os import getcwd as _pwd

_app = lambda _argv : (_cd(_argv[0]), print('#{repr(read('AUTHER.md'))}\n{read('README.md')}'), _cd(_argv[1]))
main = lambda : _app((input(), _pwd()))

if __name__ == "__main__": main()
```

will make cython+XS(perl+c)+sed

compile 2 README.md

# === [dre] === #

$1.dre -(drec.py)-> $1°<-can set $2°/directory.rem

*.dre
```fto
[AUTHER]
°AUTHER.md src°
[README]
°README.md src°
```

will make cython+sed

# === [ tmx ] === #
fto -> make sub-namespace

# === [ project.toml (pto) °dir as ns° ] === #
• MOUNT
=> MOUNT ["$°k°", "$°v°"]
• LOC RESOURCE > RESOURCE.LOC
=> LOC RESOURCE °k° $°v°
• UNI RESOURCE > RESOURCE.UNI
=> UNI RESOURCE °k° $°v°
• RESOURCE ADD > RESOURCE.ADD
=> ADD RESOURCE °k° $°v°

compile into datapack.do(cker)f(ile) (ddf)

# === [ settings.fto = (sft) °dir as ns° ] === #

JUST ENV VAR SET

# === [ base.txt = (bas) °dir as ns° ] === #

simmuar that requires.txt

basc
```sh
#!/bin/sh
read inpv
echo -n "FROM "
echo $inpv
```

# === [ ddf ] === #

MOUNT == VOLIUM
LOC RESOURCE == COPY
UNI RESOURCE == +I) url ADD
ADD RESOURCE == ADD

~.ddf compile into:
~/Dockerfile
```dockerfile
FROM ~_base

°another src°
```

# === [ tool deployment ] === #

MyDockerfileTool (compilers)
MDTprjter (by using pydockerNpygit2) (prj)
MDTPDocker-py : pypi
MDTPDocker Deployer (gh repo) (by MDTP -> MDTPDocker) 
MDTPDocker : Docker +  MDTprjter Env

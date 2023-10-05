# ✅ WARMUPS - CaesarMirror

| Key | Value |
| --- | --- |
| ID | 24 |
| Solves | 474 |
| Value | 50 |

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

Files:

- [caesarmirror.txt](https://huntress.ctf.games/files/869c3f4a516cfbfcc05934cd99de357e/caesarmirror.txt?token=eyJ1c2VyX2lkIjozMTgyLCJ0ZWFtX2lkIjo0MDcsImZpbGVfaWQiOjM4fQ.ZR7Qxw.3sMlC6-sGFRreHr-3eT2soRS7eY)

## Description

Author: @JohnHammondCaesar caesar, on the wall, who is the fairest of them all?  Perhaps a clever ROT13?  NOTE: this flag does not follow the usual MD5 hash standard flag format. It is still wrapped with the code>flag{}` prefix and suffix.  Download the file(s) below.

## Writeup

We're given a large block of text. The right side is reversed. The left side is caesar ciphered.

```text
     Bu obl! Jbj, guvf jnezhc punyyratr fher   bf V !erugrtbg ghc bg ahs sb gby n fnj
    qrsvavgryl nofbyhgryl nyjnlf ybir gelvat   ftavug rivgnibaav qan jra ch xavug bg
       gb qb jvgu gur irel onfvp, pbzzba naq   sb genc gfevs ruG !frhdvauprg SGP pvffnyp
     lbhe synt vf synt{whyvhf_ naq gung vf n   tavuglerir gba fv gv gho gengf gnret
 gung lbh jvyy arrq gb fbyir guvf punyyratr.    qan rqvu bg tavleg rxvy g'abq V
  frcnengr rnpu cneg bs gur synt. Gur frpbaq   bq hbl gho _n_av fv tnys rug sb genc
   arrq whfg n yvggyr ovg zber. Jung rknpgyl   rxnz qan leg bg reru rqhypav rj qyhbuf
     guvf svyyre grkg ybbx zber ratntvat naq   ?fravyjra qqn rj qyhbuF ?ryvujugebj
    Fubhyq jr nqq fcnprf naq gel naq znxr vg   uthbar fv fravy lanz jbU ?ynpvegrzzlf
 gb znxr guvf svyyre grkg ybbx oryvrinoyr? N    n avugvj ferggry sb renhdf qvybf
 fvzcyr, zbabfcnpr-sbag grkg svyr ybbxf tbbq   rug gn gfbzyn rj reN .rz bg uthbar
   raq? Vg ybbxf yvxr vg! V ubcr vg vf tbbq.   }abvgprysre fv tnys ehbl sb genc qevug ruG
naq ng guvf cbvag lbh fubhyq unir rirelguvat   ebs tnys fvug gvzohf bg qrra hbl gnug
    cbvagf. Gur ortvaavat vf znexrq jvgu gur   ,rpneo lyehp tavarcb rug qan kvsrec tnys
  naq vg vapyhqrf Ratyvfu jbeqf frcnengrq ol   lyehp tavfbyp n av qar bg ,frebpferqah
  oenpr. Jbj! Abj GUNG vf n PGS! Jub xarj jr   fvug bg erucvp enfrnp rug xyvz qyhbp
            rkgrag?? Fbzrbar trg gung Whyvhf   !ynqrz n lht enfrnP
```

Let's fix the left first.

```text
     Bu obl! Jbj, guvf jnezhc punyyratr fher
    qrsvavgryl nofbyhgryl nyjnlf ybir gelvat
       gb qb jvgu gur irel onfvp, pbzzba naq
     lbhe synt vf synt{whyvhf_ naq gung vf n
 gung lbh jvyy arrq gb fbyir guvf punyyratr.
  frcnengr rnpu cneg bs gur synt. Gur frpbaq
   arrq whfg n yvggyr ovg zber. Jung rknpgyl
     guvf svyyre grkg ybbx zber ratntvat naq
    Fubhyq jr nqq fcnprf naq gel naq znxr vg
 gb znxr guvf svyyre grkg ybbx oryvrinoyr? N
 fvzcyr, zbabfcnpr-sbag grkg svyr ybbxf tbbq
   raq? Vg ybbxf yvxr vg! V ubcr vg vf tbbq.
naq ng guvf cbvag lbh fubhyq unir rirelguvat
    cbvagf. Gur ortvaavat vf znexrq jvgu gur
  naq vg vapyhqrf Ratyvfu jbeqf frcnengrq ol
  oenpr. Jbj! Abj GUNG vf n PGS! Jub xarj jr
            rkgrag?? Fbzrbar trg gung Whyvhf
```

```text
  Oh boy! Wow, this warmup challenge sure
   definitely absolutely always love trying
      to do with the very basic, common and
    your flag is flag{julius_ and that is a
that you will need to solve this challenge.
 separate each part of the flag. The second
  need just a little bit more. What exactly
    this filler text look more engaging and
   Should we add spaces and try and make it
to make this filler text look believable? A
simple, monospace-font text file looks good
  end? It looks like it! I hope it is good.
and at this point you should have everything
   points. The beginning is marked with the
 and it includes English words separated by
 brace. Wow! Now THAT is a CTF! Who knew we
           extent?? Someone get that Julius
```

And now the left side needs to be mirrored first:

```text
jnf n ybg bs sha gb chg gbtrgure! V fb
gb guvax hc arj naq vaabingvir guvatf
pynffvp PGS grpuavdhrf! Gur svefg cneg bs
terng fgneg ohg vg vf abg rirelguvat
V qba'g yvxr gelvat gb uvqr naq
cneg bs gur synt vf va_n_ ohg lbh qb
fubhyq jr vapyhqr urer gb gel naq znxr
jbegujuvyr? Fubhyq jr nqq arjyvarf?
flzzrgevpny? Ubj znal yvarf vf rabhtu
fbyvq fdhner bs yrggref jvguva n
rabhtu gb zr. Ner jr nyzbfg ng gur
guveq cneg bs lbhe synt vf ersyrpgvba}
gung lbh arrq gb fhozvg guvf synt sbe
synt cersvk naq gur bcravat pheyl oenpr,
haqrefpberf, gb raq va n pybfvat pheyl
pbhyq zvyx gur pnrfne pvcure gb guvf
Pnrfne thl n zrqny!
```

then caesar unciphered:

```text
was a lot of fun to put together! I so
to think up new and innovative things
classic CTF techniques! The first part of
great start but it is not everything
I don't like trying to hide and
part of the flag is in_a_ but you do
should we include here to try and make
worthwhile? Should we add newlines?
symmetrical? How many lines is enough
solid square of letters within a
enough to me. Are we almost at the
third part of your flag is reflection}
that you need to submit this flag for
flag prefix and the opening curly brace,
underscores, to end in a closing curly
could milk the caesar cipher to this
Caesar guy a medal!
```

Now smash them together and parse out the flag bits.

```text
     Oh boy! Wow, this warmup challenge sure so I together! put to fun of lot a was
    definitely absolutely always love trying things innovative and new up think to
       to do with the very basic, common and of part first The techniques! CTF classic
     your flag is flag{julius_ and that is a everything not is it but start great
 that you will need to solve this challenge. and hide to trying like don't I
  separate each part of the flag. The second do you but in_a_ is flag the of part
   need just a little bit more. What exactly make and try to here include we should
     this filler text look more engaging and newlines? add we Should worthwhile?
    Should we add spaces and try and make it enough is lines many How symmetrical?
 to make this filler text look believable? A a within letters of square solid
 simple, monospace-font text file looks good the at almost we Are me. to enough
   end? It looks like it! I hope it is good. reflection} is flag your of part third The
and at this point you should have everything for flag this submit to need you that
    points. The beginning is marked with the brace, curly opening the and prefix flag
  and it includes English words separated by curly closing a in end to underscores,
  brace. Wow! Now THAT is a CTF! Who knew we this to cipher caesar the milk could
            extent?? Someone get that Julius medal! a guy Caesar
```

Get the flag by piecing it together:

`flag{julius_in_a_reflection}`

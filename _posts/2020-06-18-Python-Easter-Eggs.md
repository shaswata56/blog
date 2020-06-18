---
title: My favourite Python Easter Eggs
published: true
---

*   ### Builtin - hello world

```py
>>> import __hello__
```
```
Hello World!
```

*   ### The Zen

```py
>>> import this
```
```
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```
```py
>>> love = this
>>> this is love
```
```
True
```
```py
>>> love is True
```
```
False
```
```py
>>> love is False
```
```
False
```
```py
>>> love is not True or False
```
```
True
```
```py
>>> love is love
```
```
True
```

*   ### Paradoxical - this.py

```py
s = """Gur Mra bs Clguba, ol Gvz Crgref
Ornhgvshy vf orggre guna htyl.
Rkcyvpvg vf orggre guna vzcyvpvg.
Fvzcyr vf orggre guna pbzcyrk.
Pbzcyrk vf orggre guna pbzcyvpngrq.
Syng vf orggre guna arfgrq.
Fcnefr vf orggre guna qrafr.
Ernqnovyvgl pbhagf.
Fcrpvny pnfrf nera'g fcrpvny rabhtu gb oernx gur ehyrf.
Nygubhtu cenpgvpnyvgl orngf chevgl.
Reebef fubhyq arire cnff fvyragyl.
Hayrff rkcyvpvgyl fvyraprq.
Va gur snpr bs nzovthvgl, ershfr gur grzcgngvba gb thrff.
Gurer fubhyq or bar-- naq cersrenoyl bayl bar --boivbhf jnl gb qb vg.
Nygubhtu gung jnl znl abg or boivbhf ng svefg hayrff lbh'er Qhgpu.
Abj vf orggre guna arire.
Nygubhtu arire vf bsgra orggre guna *evtug* abj.
Vs gur vzcyrzragngvba vf uneq gb rkcynva, vg'f n onq vqrn.
Vs gur vzcyrzragngvba vf rnfl gb rkcynva, vg znl or n tbbq vqrn.
Anzrfcnprf ner bar ubaxvat terng vqrn -- yrg'f qb zber bs gubfr!"""

d = {}
for c in (65, 97):
    for i in range(26):
        d[chr(i+c)] = chr((i+13) % 26 + c)

print("".join([d.get(c, c) for c in s]))
```

The Zen showed it's paradox in the source. It's not beautiful but ugly, not explicit but implicit. This would probably be the only module to go against the spirit of what it says itself..

*   ### Let's take a tour in space

```py
>>> import antigravity
```
![Antigravity](https://imgs.xkcd.com/comics/python.png)


*   ### Never try to bring curly braces from future

```py
>>> from __future__ import braces
  File "<stdin>", line 1
SyntaxError: not a chance
```

*   ### Don't go deep!

```py
>>> import types
>>> help(types.CodeType)

Help on class code in module builtins:

class code(object)
 |  code(argcount, posonlyargcount, kwonlyargcount, nlocals, stacksize,
 |        flags, codestring, constants, names, varnames, filename, name,
 |        firstlineno, lnotab[, freevars[, cellvars]])
 |  
 |  Create a code object.  Not for the faint of heart.
 |  
 |  Methods defined here:
 |  
 |  __eq__(self, value, /)
 |      Return self==value.
 |  
 |  __ge__(self, value, /)
 |      Return self>=value.
 |  
 |  __getattribute__(self, name, /)
 |      Return getattr(self, name).
 |  
 |  __gt__(self, value, /)
 |      Return self>value.
 |  
 |  __hash__(self, /)
 |      Return hash(self).
 |  
 |  __le__(self, value, /)
 |      Return self<=value.
 |  
 |  __lt__(self, value, /)
 |      Return self<value.
 |  
 |  __ne__(self, value, /)
 |      Return self!=value.
 |  
 |  __repr__(self, /)
 |      Return repr(self).
 |  
 |  __sizeof__(...)
 |      Size of object in memory, in bytes.
 |  
 |  replace(self, /, *, co_argcount=-1, co_posonlyargcount=-1, co_kwonlyargcount=-1, co_nlocals=-1, co_stacksize=-1, co_flags=-1, co_firstlineno=-1, co_code=None, co_consts=None, co_names=None, co_varnames=None, co_freevars=None, co_cellvars=None, co_filename=None, co_name=None, co_lnotab=None)
 |      Return a copy of the code object with new values for the specified fields.
```
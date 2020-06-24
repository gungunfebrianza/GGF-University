# Compiler Construction

## Gun Gun Febrianza

## Setup Development Tools

### Installation Prerequisites

- **Install AntlrVSIX** - [here](https://marketplace.visualstudio.com/items?itemName=KenDomino.AntlrVSIX)

- **Install Oracle JDK & JRE** - [here](https://www.oracle.com/technetwork/java/javase/downloads/index.html)

- **Install Java-based Antlr Toolchain** - [here](https://www.antlr.org/download/antlr-4.8-complete.jar)

- **Setup Environment Variable** :

  - JAVA_HOME

  - ```
    C:\Program Files\Java\jdk-14.0.1
    ```

  - JRE_HOME

  - ```
    C:\Program Files\Java\jre1.8.0_251
    ```

  - JAVA_EXEC

  - ```
    C:\Program Files\Java\jdk-14.0.1\bin\java.exe
    ```

  - Antlr4ToolPath

  - ```
    C:\antlr\antlr-4.8-complete.jar
    ```

### Verify Prerequisites

Execute this command under cmd.exe :

```
"%JAVA_EXEC%" -jar "%Antlr4ToolPath%" 
```

### Antlr Project

1. Open Visual Studio 2019
2. Create a new project
3. AntlrFAProject
4. Run The Project

### Antlr Dashboard

- Antlr Documentation - [here](https://github.com/antlr/antlr4/blob/4.8/doc/index.md)

----------------

## Syntax

Sebuah bahasa memiliki sekumpulan **string** yang terdiri dari sekumpulan **character** dari sebuah **alphabet**. 

**Alphabet** adalah **finite set** dari sebuah **symbol** dan **symbol** adalah **unit** yang menjadi representasi data. 

Contoh **Alphabet** yang berisi **finite set of symbol**.

> Σ = {*a*, *b*, *c*}

Setiap **string** dari bahasa tersebut disebut dengan **sentence** atau **statement**. 

**String** adalah serangkaian terbatas **symbol** dari sebuah **alphabet**. 

Contoh **String** :

> w = abbcbabb, x = bb, y = aa                 

Sebuah **string** memiliki **property** **length** yang digunakan untuk mengetahui jumlah kemunculan **symbol** di dalam suatu **string**. 

Contoh **length of string**.

> Jika w = abbac, maka |w| = 5               

**Syntax** mengacu ke bagaimana cara sekumpulan **symbol** digabungkan untuk membentuk sebuah kalimat dari sebuah bahasa. 

**Syntax** menjelaskan relasi formal dengan unsur suatu bahasa, menyediakan deskripsi struktural dari berbagai ekpresi yang merupakan sebuah legal **string** dalam sebuah bahasa. **Syntax** hanya mengatur bentuk dan struktur sebuah **symbol** dalam sebuah bahasa tanpa mempertimbangkan maknanya [1]. 

Oleh karena itu legal atau tidaknya suatu **string** dalam sebuah bahasa yang ingin dibuat harus ditetapkan terlebih dahulu. Sebagai contoh terdapat sebuah bahasa **x** yang mengatur tentang legalitas **syntax** yang dimilikinya.

| Legal dalam bahasa x          | Ilegal dalam bahasa x |
| ----------------------------- | --------------------- |
| "Hello Maudy Ayunda"          | "Hello Maudy Ayunda   |
| 666                           | 666)                  |
| 13\*(31/9+7-0)/(80/2+14+9\*3) | 9*(13////)/(5+---+))  |
| 8*(((9-6)))                   | +2+9                  |

### Syntax Rule

**Syntax Rule** dari sebuah bahasa menentukan **string** mana yang merupakan bagian dari bahasa tersebut. 

Sebuah bahasa bisa memiliki sekumpulan **string** yang terbatas dan tidak terbatas, sebagai contoh jika **L** dan **M** adalah sebuah bahasa dimana **L = {xor, xix, xyz}** dan **M = {ex, xix}** maka ada beberapa operasi yang bisa dilakukan pada bahasa tersebut. 

1. ***Union*** L∪M = {xor, xix, xyz, ex}                        
2. ***Concatenation*** LM = {xorex, xorxix, xixex, xixxix, xyzex, xyzxix}
3. ***Exponentiation*** L<sup>2</sup> = LL
4. ***Definition*** L<sup>0</sup> = {∈} dan L<sup>1</sup> = L

#### Kleene Closure

**Kleene closure** dari bahasa L dinotasikan dengan L<sup>*</sup> yang artinya kosong atau terdapat lebih dari 1 dari L.

> L<sup>*</sup> = L<sup>0</sup> ∪ L<sup>1</sup> ∪ L<sup>2</sup> ∪ L<sup>3</sup> . . . ∪ L<sup>n</sup> . . .                        

Sebagai contoh jika **L = {a,b}** maka jika L<sup>*</sup> :

> L<sup>*</sup> = {∈, a, b, aa, ab, ab, ba, bb, aaa, aba, baa, . . . }

#### Positive Closure

**Positive closure** dari bahasa L dinotasikan dengan L<sup>+</sup> yang artinya satu atau terdapat lebih dari 1 dari L.

> L<sup>+</sup> = L<sup>1</sup> ∪ L<sup>2</sup> ∪ L<sup>3</sup> . . . ∪ L<sup>n</sup> . . .    

Sebagai contoh jika **L = {a,b}** maka jika L<sup>+</sup> :

> L<sup>+</sup> = {a, b, aa, ba, bb, aaa, aba, . . . }

#### Prefix

**Prefix** adalah sebuah **string** yang diperoleh dengan cara menghapus 0 atau lebih dari 1 akhiran **symbol** dalam sebuah **string**. 

Contoh : **RA** adalah **Prefix** dari **RAM**.

#### Suffix

**Suffix** adalah sebuah **string** yang diperoleh dengan cara menghapus 0 atau lebih dari 1 awalan **symbol** dalam sebuah **string**. 

Contoh : **AM** adalah **Suffix** dari **RAM**.

#### Substring

**Substring** adalah sebuah **string** dengan cara menghapus **prefix** atau **suffix** dari sebuah **string**. 

Contoh **RA** atau **AM** adalah **substring** dari **RAM**.

## Regular Expression

**Regular Expression** adalah **text pattern** yang menjelaskan bagaimana bentuk **string** [2]. 

Ekspresi tersebut bisa diimplementasikan dalam sebuah **software** menggunakan **Deterministic Finite Automata (DFA)** [3]. 

Di bawah ini adalah contoh notasi **regular expression**.

> Letter (letter|digit)

Setiap **regular expression** ‘r’ menunjukan bahasa ‘L(r)’. 

Sebuah bahasa yang dinotasikan oleh **regular expression** disebut dengan **regular set**. 

**Regular expression** sangat berguna untuk merepresentasikan sekumpulan **string** dalam bentuk **algebraic fashion**. 

**Regular expression** pada sebuah **alphabet** menentukan bahasa dengan mengacu kepada aturan-aturan sebagai berikut.

1. ε adalah sebuah **Regular Expression** yang dinotasikan dengan {ε} bahwa di dalamnya hanya terdapat **set empty string**.
2. Jika *a* adalah sebuah *symbol* dalam *alphabet*, maka *a* adalah *regular* *expression* yang dinotasikan dengan {*a*} bahwa di dalamnya terdapat *set* yang terdiri dari *string* *a*.
3. Dikatakan ‘*r*’ dan ‘*s*’ adalah *regular expression* yang dinotasikan dengan L(*r*) dan L(*s*), maka :
   - (*r*)|(*s*) adalah *regular expression* dengan notasi L(r) ∪ L(s)
   - (*r*)(*s*) adalah *regular expression* dengan notasi L(r)L(s)
   - (*c*) (*r*)\* adalah RE dengan notasi (L(r))*

Contoh operasi aljabar dalam **regular expression**, dikatakan bahwa r, s dan t adalah **regular expression** dengan notasi L(r) L(s) L (t) maka  :

1. *r* | *s* adalah RE dengan notasi L(*r*) ∪ L(*s*). ( | ) komutatif.
2. *r* | (*s* | *t* ) = ( *r* | *s* ) | *t*. ( | ) asosiatif.   
3. (*rs*) *t* = *r* ( *st* ). Disini *concatenation* adalah asosiatif.
4. *r* (*s* | *t*) = *rs* | *rt* . Disini *concatenation* adalah distributif.
5. *εr* = *r* = *rε*. Disini ε adalah identitas *element*.
6. r\* = (*r* | *ε*)*    

Contoh **Regular Expression** :

| Regex              | Result                                        |
| ------------------ | --------------------------------------------- |
| Hello              | {Hello}                                       |
| love \| hate       | {love, hate}                                  |
| Li (f\|v) e        | {Life, Live}                                  |
| li[fv]e            | {life, live}                                  |
| [b-chm-pP]at\|ot   | {bat, cat, hat, mat, pat, Pat, Pot}           |
| colou?r            | {color, colour}                               |
| rege(x(es)?\|xps?) | {regex, regexes, regexp, regexps}             |
| go*gle             | {gle, gogle, google, gooogle, goooogle, ...}  |
| go+gle             | {gogle, google, gooogle, goooogle, ...}       |
| g(oog)+le          | {google , googoogoogle, googoogoogoogle, ...} |
| z{3}               | {zzz}                                         |
| z{3,6}             | {zzz, zzzz, zzzzz, zzzzzz}                    |
| z{3,}              | {zzz, zzzz, zzzzz, ...}                       |

### Regular Definition

**Regular Definition** adalah nama yang diberikan untuk **regular expression** tertentu dan menggunakan nama tersebut dalam **regular expression** lainya [4]. 

Sebagai contoh di bawah ini adalah **regular definition** yang menjadi **set** untuk **identifier** dalam bahasa pemrograman umumnya yang dijelaskan sebagai dari sekumpulan **string of letter** dan **digit** yang diawali dengan **letter**.

## Automata

## Grammar

## Metalanguage 

## Derivation 

## Parse Tree

## Extended Backus Naus Form (EBNF) 

## Syntax Diagram 

## Bibliography

[1] Slonneger & Kurtz, "Specifying Syntax", *Formal Syntax and Semantics of Programming Languages - A Laboratory Based Approach,*  USA : Addison-Wesley, 1994. pp 1

[2] Felix & Victor, "Introducing Regular Expression", *Mastering Python Regular Expression,* Mumbai, : Packt Publisher, 2014. pp 5

[3] Goyvaerts & Levithan*,* "Introduction to Regular Expression", *O’reilly. Regular Expression Cockbook,* USA : O’Reilly 2009. pp.2

[4] Singh*,* Ravendra, Varshney, Manish and Sharma, Vivek. "Introduction to Compiler", *Design and Implementation of Compiler,* New Delhi *:* New Age International Publisher, 2010. pp 43
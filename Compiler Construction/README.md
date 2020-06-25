# Compiler Construction

## Gun Gun Febrianza

## Content Table

1. Setup Development Tools
   - Installation Prerequisites
   - Verify Prerequisites
   - Antlr Project
   - Antlr Dashboard
2. Syntax
   - Syntax Rule
     - Kleene Closure
     - Positive Closure
     - Prefix
     - Suffix
     - Substring
3. Regular Expression
   - Regular Definition
4. Automata
   - Deterministic Finite Automaton (DFA)
5. Grammar
   - Formal Method
6. Metalanguage
7. Derivation
8. Parse Tree
9. EBNF
10. Syntax Diagram

## Setup Development Tools

### Installation Prerequisites

- **Install AntlrVSIX** - [here](https://marketplace.visualstudio.com/items?itemName=KenDomino.AntlrVSIX)

- **Install Oracle JDK & JRE** - [here](https://www.oracle.com/technetwork/java/javase/downloads/index.html)

- **Install Java-based Antlr Toolchain** - [here](https://www.antlr.org/download/antlr-4.8-complete.jar)

- **Setup Environment Variable** :

  - **JAVA_HOME**

  - ```
    C:\Program Files\Java\jdk-14.0.1
    ```

  - **JRE_HOME**

  - ```
    C:\Program Files\Java\jre1.8.0_251
    ```

  - **JAVA_EXEC**

  - ```
    C:\Program Files\Java\jdk-14.0.1\bin\java.exe
    ```

  - **Antlr4ToolPath**

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

1. **Union** L ∪ M = {xor, xix, xyz, ex}                        
2. **Concatenation** LM = {xorex, xorxix, xixex, xixxix, xyzex, xyzxix}
3. **Exponentiation** L<sup>2</sup> = LL
4. **Definition** L<sup>0</sup> = {∈} dan L<sup>1</sup> = L

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

> Contoh : **RA** adalah **Prefix** dari **RAM**.

#### Suffix

**Suffix** adalah sebuah **string** yang diperoleh dengan cara menghapus 0 atau lebih dari 1 awalan **symbol** dalam sebuah **string**. 

> Contoh : **AM** adalah **Suffix** dari **RAM**.

#### Substring

**Substring** adalah sebuah **string** dengan cara menghapus **prefix** atau **suffix** dari sebuah **string**. 

> Contoh **RA** atau **AM** adalah **substring** dari **RAM**.

## Regular Expression

**Regular Expression** adalah **text pattern** yang menjelaskan bagaimana bentuk suatu **string** [2]. 

Ekspresi tersebut bisa diimplementasikan dalam sebuah **software** menggunakan **Deterministic Finite Automata (DFA)** [3]. 

Di bawah ini adalah contoh notasi **Regular Expression**.

> Letter (letter|digit)

Setiap **Regular Expression** ‘r’ menunjukan bahasa ‘L(r)’. 

Sebuah bahasa yang dinotasikan oleh **Regular Expression** disebut dengan **Regular Set**. 

**Regular Expression** sangat berguna untuk merepresentasikan sekumpulan **string** dalam bentuk **Algebraic Fashion**. 

**Regular Expression** pada sebuah **alphabet** menentukan bahasa dengan mengacu kepada aturan-aturan sebagai berikut.

1. **ε** adalah sebuah **Regular Expression** yang dinotasikan dengan {ε} bahwa di dalamnya hanya terdapat **set empty string**.
2. Jika *a* adalah sebuah **symbol** dalam **alphabet**, maka *a* adalah **Regular Expression** yang dinotasikan dengan {*a*} bahwa di dalamnya terdapat **set** yang terdiri dari **string** *a*.
3. Dikatakan ‘*r*’ dan ‘*s*’ adalah **Regular Expression** yang dinotasikan dengan L(*r*) dan L(*s*), maka :
   - (*r*)|(*s*) adalah **Regular Expression** dengan notasi L(r) ∪ L(s)
   - (*r*)(*s*) adalah **Regular Expression** dengan notasi L(r)L(s)
   - (*c*) (*r*)\* adalah **Regular Expression** dengan notasi (L(r))*

Contoh operasi aljabar dalam **Regular Expression**, 

Dikatakan bahwa r, s dan t adalah **Regular Expression** dengan notasi L(r) L(s) L (t) maka  :

1. *r* | *s* adalah **Regular Expression** dengan notasi L(*r*) ∪ L(*s*). ( | ) komutatif.
2. *r* | (*s* | *t* ) = ( *r* | *s* ) | *t*. ( | ) asosiatif.   
3. (*rs*) *t* = *r* ( *st* ). Disini **concatenation** adalah asosiatif.
4. *r* (*s* | *t*) = *rs* | *rt* . Disini **concatenation** adalah distributif.
5. *εr* = *r* = *rε*. Disini ε adalah identitas **element**.
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

**Regular Definition** adalah nama yang diberikan untuk **Regular Expression** tertentu dan menggunakan nama tersebut dalam **regular expression** lainya [4]. 

Sebagai contoh di bawah ini adalah **regular definition** yang menjadi **set** untuk **identifier** dalam bahasa pemrograman umumnya yang dijelaskan sebagai dari sekumpulan **string of letter** dan **digit** yang diawali dengan **letter**.

> letter → A | B | . . . | Z | a | b | . . . | z	

> digit → 0 | 1 | 2 | . . . | 9	

> id →  letter(letter | digit)*

Pada **Regular Expression** id adalah **pattern** untuk **identifier** yang terdiri dari **letter** dan **digit**. 

Dimana **letter** adalah **Regular Expression** untuk **set of all upper-case** dan **lower-case letters** pada sebuah **alphabet** dan **digit** adalah **Regular Expression** untuk **set of all decimal digits**.



## Automata

Proses Penerimaan **String** oleh **Finite Automaton** [5] 



**Automata** atau **automaton** adalah model abstrak dari komputer digital. 

Sebuah **Automaton** memiliki mekanisme untuk membaca **input**, dimana **input** tersebut adalah **string** dari sebuah **alphabet**. Input ini secara aktual ditulis pada sebuah “input file”, yang hanya bisa dibaca oleh **automaton** tanpa memiliki kemampuan untuk mengubahnya. 

**Input file** dibagi menjadi beberapa sel, setiap sel dapat menampung satu **symbol**. **Automaton** juga memiliki alat penyimpanan sementara yang memiliki sel dengan jumlah tak terbatas, kontenya dapat diubah oleh **automaton**. 

**Automaton** memiliki **control unit**, yang di dalamnya terdapat **finite number** dari sebuah **internal state**. 

**Automaton** dapatmengubah **state** dengan cara yang telah ditentukan. 

Di bawah ini adalah contoh figure **automaton**.

Jika **internal state**, **input** dan konten dari penyimpanan telah diketahui, maka karakteristik **automaton** bisa diprediksikan sehingga disebut **deterministic automata**. Pada sebuah **automaton** terdapat **acceptor** yang merespon ya atau tidak pada **output**. 

### Deterministic Finite Automaton

Contoh **Deterministic Finite Automaton  (DFA)** :

Sebuah *DFA* terdiri dari 5 Tuple *M* = (*Q*, S,d, *q* , *F* )

Q = *Finite set* dari *“internal state”*

Σ = *Finite set* *symbol* yang dipanggil “*input alphabet*”

δ = *lowercase delta* sebagai notasi fungsi **transition**

q0 ∈ Q = q0 elemen dari Q yang menjadi **start state**

F ⊆ Q = F *single* elemen atau **subset** dari **set** Q untuk *final state*

Mekanisme **input** hanya mampu bergerak dari kiri kekanan dan hanya membaca satu **symbol** untuk setiap langkahnya. 

**Transition** dari satu **internal state** ke **state** lainya diatur oleh fungsi *transition* δ. 

Jika δ (*q*0 , *a*) *q*1, maka jika **Deterministic Finite Automaton** berada pada *state* *q*0 dan *input symbol* saat ini adalah *a* maka **Deterministic Finite Automaton** akan melaju ke *state* *q*1. 

Sebagai contoh terdapat desain **Deterministic Finite Automaton**, dengan M yang hanya bisa menerima bahasa L(M) = *w*∈(*a*, *b*)* dengan syarat *w* tidak boleh mengandung tiga **consecutive** b’s. Maka *M* = (*Q*, S, d, *q* , *F* ) dimana :

*Q* = {*q*0, *q*1, *q*2, *q*3}

S = {*a*, *b*}

*q*0 sebagai **initial state**

*F* = {*q*0, *q*1, *q*2,} adalah **final states** dan fungsi transisi d adalah sebagai berikut:



## Grammar

Secara umum bahasa bisa didefinisikan dengan dua cara yang berbeda yaitu sebagai **recognition** dan **generation** [6]. 

Sebagai contoh pada **Language Recognizer**, dikatakan bahwa kita memiliki sebuah bahasa yang disebut dengan L dan L menggunakan **alphabet** Σ yang berisi sekumpulan **character**. Untuk menjelaskan L secara formal menggunakan metode pengenal (**recognition method**) maka harus membangun konstruksi untuk R yang disebut sebagai alat pengenal.

Alat pengenal ini mempunyai kemampuan untuk membaca **string of character** dari sebuah **alphabet** Σ. 

R akan menunjukan apakah suatu **string input** yang diberikan itu ada atau tidak di dalam L. 

Efek lainya R mempunyai kapasitas untuk menolak dan menerima **string** yang diberikan. Alat seperti itu disebut dengan **filter** untuk memisahkan **statement** yang legal dari **statement** yang tidak legal.

Ketika R menerima **input string** dari karakter yang berada pada **alphabet** Σ dan hanya menerima ketika ada di dalam L, maka R adalah deskripsi dari L. 

### Formal Method

Pada **Language Generator** sebuah **statements** dari suatu bahasa bisa dibuat, **Formal Method** untuk mendefinisikan suatu **syntax** dari bahasa pemrograman disebut dengan **grammar**. **Formal Method** lebih sukses menjelaskan tentang **syntax** sebuah bahasa pemrograman daripada **semantic** sebuah bahasa pemrograman. 

Mendefinisikan **syntax** bahasa pemrograman hampir mirip dengan merumuskan tata bahasa yang ada pada **Natural Language**. Menjelaskan bagaimana sebuah **symbol** dapat dibentuk kedalam **phrase** bahasa yang valid. **Formal Grammar** yang diusulkan oleh **Noam Chomsky** untuk **Natural Language** juga bisa diterapkan kedalam bahasa pemrograman.

Sebuah **Grammar** terdiri dari empat bagian **< S,N,P,S>** :

1. **Finite Set** S sebuah **Terminal Symbol** yaitu **alphabet** dari bahasa yang digabungkan untuk membentuk sebuah **statements** atau **sentences** dalam sebuah bahasa. 

2. **Finite Set** N sebuah **Nonterminal Symbol** atau **syntactic categories** masing masingnya merepresentasikan koleksi **subphrase** dari sebuah **statements** atau **sentences**.

3. **Finite Set** P yang menjadi sebuah **Production** atau **Rules** untuk menjelaskan bagaimana setiap **nonterminal** dijelaskan dalam **term** dari **terminal symbol** atau **nonterminal symbol**. Pilihan **nonterminal** menentukan **phrase** bahasa yang kita anggap memiliki makna.

4. **Nonterminal** S yang menjadi **start symbol**.



## Metalanguage 

**Metalanguage** adalah sebuah bahasa yang digunakan untuk menggambarkan bahasa lain. 

**Backus-Naur Form (BNF)** adalah sebuah **metalanguage**. Untuk membentuk **syntactic structure BNF** menggunakan **abstraction**. Sebagai contoh pada **assignment statement** (penetapan nilai) bahasa **java**, direpresentasikan dengan **abstraction** **< assign>**, defini aktual **< assign>** pada java adalah sebagai berikut.

```
<assign> → <var> = <expression>
```

Teks yang berada disebelah kiri disebut dengan **LHS** (**Left-hand Side**) adalah **abstraction** yang didefinisikan. Teks yang ada disebelah kanan adalah **RHS** (**Right-hand Side**) terdiri dari gabungan sebuah **token**, **lexeme** dan referensi **abstraction** lainya. 

Keseluruhanya disebut dengan **rule** atau **production**. 

**Rule** ini bisa menspesifikasikan bahwa **< assign>** telah dijelaskan sebagai salah satu **abstraction** dari **< var>**, yang diikuti dengan **lexemes** = dan diikuti dengan **abstraction** dari **< expression>**, contoh satu **sentence syntactical structure** dari **rule** di atas adalah sebagai berikut.

```
Total = total1 + total2
```

**Abstractions** dari deskripsi **Backus-Naur Form**, atau **grammar**, seringkali dipanggil **nonterminal symbols**, atau **nonterminal** saja dan **lexemes** juga **tokens** dari **rule** dipanggil dengan terminal **symbols**. Di dalam **grammar** terdapat sekumpulan koleksi **rule**. 

**Nonterminal symbols** bisa memiliki dua atau lebih definisi yang berbeda, merepresentasikan dua atau lebih kemungkinan bentuk **syntactic** dari suatu bahasa. Multi definisi bisa ditulis sebagai sebuah **single rule**, setiap definisi yang berbeda dipisahkan oleh **symbol** **|**, yang artinya atau. 

Sebagai contoh, pada bahasa **Java** sebuah **if statement** bisa dijelaskan dengan **rules** sebagai berikut.

```
<if_stmt> → if ( <logic_expr> ) <stmt>
<if_stmt> → if ( <logic_expr> ) <stmt> else <stmt>
```

Atau dengan **rule** :

```
<if_stmt> → if ( <logic_expr> ) <stmt> | if ( <logic_expr> ) <stmt> else <stmt>
```

Pada **rule** ini, **< stmt>** merepresentasikan **single statement** atau **compound statement**. Meskipun **BNF** sangat sederhana, ini cukup **powerful** untuk menggambarkan lebih dekat semua **syntax** yang ada di dalam bahasa pemrograman. Secara khusus, bisa menggambarkan **list** konstruksi yang sama, konstruksi mana saja yang harus didahulukan, struktur bersarang sedalam apapun, mengenali **operator precedence** dan **associative**.

Pada matematika panjang sebuah variable dinotasikan di dalam **ellipsis** (…); 1,2..n sebagai contoh. Untuk menjelaskan sebuah **list BNF** tidak menerima **ellipsis** jadi metode alternatif dibutuhkan untuk menggambarkan **list** secara **syntactic** dalam bahasa pemrograman adalah **recursion**. 

**Recursion** digunakan untuk menggambarkan **list** di dalam banyak **grammar**. Sebuah **rule** dikatakan **recursive** jika **LHS** yang dimilikinya muncul di **RHS**. **Rules** di bawah ini adalah ilustrasi bagaimana sebuah **recursion** digunakan untuk menggambarkan sebuah **list**.

```
<ident_list> → identifier | identifier, <ident_list>
```

## Derivation 

Sebuah **Grammar** bekerja seperti **Generative Device** untuk mendefinisikan sebuah bahasa. Kalimat dari bahasa mampu dihasilkan melalui urutan aplikasi dari sebuah **Production Rule**, diawali dengan **Special Nonterminal** dari **Grammar** yang dikenal dengan **start symbol**. Urutan dari aplikasi **Production Rule** ini disebut dengan **Derivation**. 

Di dalam sebuah **Grammar** bahasa pemrograman yang sudah lengkap, **Start Symbol** merepresentasikan program yang telah komplit. Contoh **Grammar** **X** yang akan digunakan untuk mengilustrasikan **Derivation**.

Contoh **Grammar X** :

| Rules | Grammar                                                      |
| ----- | ------------------------------------------------------------ |
| 1     | **< assign> → < id> = < expr>**                              |
| 2     | **< id> → A \| B \| C**                                      |
| 3     | **< expr> → < id> + < expr> \| < id> * < expr> \| ( < expr>) \| < id>** |

Pada **Grammar** di atas hanya terdapat satu bentuk **Statement** yaitu **assign**, diikuti dengan **identifier** yang hanya terdiri dari **A** atau **B** atau **C** dan **Expression** bisa memiliki satu atau lebih dari dua **identifier** yang dipisahkan oleh **operator** + atau *. 

**Derivation** dari program yang ada dibahasa ini adalah sebagai berikut.

**Derrivation Grammar X**

| Steps | Derivation                    |
| ----- | ----------------------------- |
| 1     | < assign> => < id> = < expr>  |
| 2     | => A = < expr>                |
| 3     | => A = < id> * < expr>        |
| 4     | => A = B * < expr>            |
| 5     | => A = B * ( < expr>)         |
| 6     | => A = B * ( < id> + < expr>) |
| 7     | => A = B * ( A + < expr>)     |
| 8     | => A = B * ( A + < id>)       |
| 9     | => A = B * ( A + C )          |



## Parse Tree

## Extended Backus Naus Form (EBNF) 

### EBNF Notation

## Syntax Diagram 

## Semantic 

## Pragmatic

## Compilation Process

### Source Code 

### Lexical Analyzer 

### Syntax Analyzer 

### Symbol Table 

### Intermediate Code Generator 

### Semantic Analyzer 

### Optimization 

### Code Generation



## Bibliography

[1] Slonneger & Kurtz, "Specifying Syntax", *Formal Syntax and Semantics of Programming Languages - A Laboratory Based Approach,*  USA : Addison-Wesley, 1994. pp 1

[2] Felix & Victor, "Introducing Regular Expression", *Mastering Python Regular Expression,* Mumbai, : Packt Publisher, 2014. pp 5

[3] Goyvaerts & Levithan*,* "Introduction to Regular Expression", *O’reilly. Regular Expression Cockbook,* USA : O’Reilly 2009. pp.2

[4] Singh*,* Ravendra, Varshney, Manish and Sharma, Vivek. "Introduction to Compiler", *Design and Implementation of Compiler,* New Delhi *:* New Age International Publisher, 2010. pp 43

[5] Levelt, "Finite Automata" *Introduction to The Theory of Formal Languages and Automata,* Amsterdam : John Benjamin Publishing Company, 2008. pp 51

[6] Sebesta, Robert, "Describing Syntax and Semantic", *Concept of Programming Languages, 7th Edition,* Malaysia, : Pearson, 2016. pp 136 
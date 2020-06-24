# Compiler Construction

## Gun Gun Febrianza

## Setup Development Tools

### Installation Prerequisites

- Install AntlrVSIX - [here](https://marketplace.visualstudio.com/items?itemName=KenDomino.AntlrVSIX)

- Install Oracle JDK & JRE - [here](https://www.oracle.com/technetwork/java/javase/downloads/index.html)

- Install Java-based Antlr Toolchain - [here](https://www.antlr.org/download/antlr-4.8-complete.jar)

- Setup Environment Variable :

  - ```
    JAVA_HOME
    ```

  - ```
    C:\Program Files\Java\jdk-14.0.1
    ```

  - ```
    JRE_HOME
    ```

  - ```
    C:\Program Files\Java\jre1.8.0_251
    ```

  - ```
    JAVA_EXEC
    ```

  - ```
    C:\Program Files\Java\jdk-14.0.1\bin\java.exe
    ```

  - ```
    Antlr4ToolPath
    ```

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



## Regular Expression

## Automata

## Grammar

## Metalanguage 

## Derivation 

## Parse Tree

## Extended Backus Naus Form (EBNF) 

## Syntax Diagram 

## Bibliography

[1] Slonneger & Kurtz, "Specifying Syntax", *Formal Syntax and Semantics of Programming Languages - A Laboratory Based Approach,*  USA : Addison-Wesley, 1994. pp 1
# Pretend to Understand Big Data

### Research Note From Gun Gun Febrianza

#### Content Table :

1. #### Infrastructure & Technology

   - ##### Distributed Data Processing

2. Reserved



**Distributed Data Processing** telah hadir menemani para **Software Architect** sejak akhir tahun 1970an. Konsep pertama yang di gagas adalah melakukan replikasi DBMS dengan konfigurasi **Master & Slave** dan memproses data menggunakan berbagai mesin komputer sekaligus.

**Problem** utama pada **Large-scale Data Processing** terbagi menjadi beberapa domain :

	1. **Concurrency**
 	2. **Fault** **Tolerance**
 	3. **Distributed Processing of Program**
 	4. **And the MPV Monster : Cost of Infrastructure**

Kenapa **Distributed Data Processing** gagal jika kita menggunakan **Relational Architecture** ?

- Ketergantungan pada DBMS
  - **ACID Compliance** untuk manajemen **Transaction**
  - **Complexity on Architecture** untuk menajemen **Consistency**
  - **Latencies** pada keseluruhan sistem :
    - Jaringan Komputer yang lamban
    - RDBMS IO
    - **SAN Architecture**
- Biaya Infrastruktur
- **Complex Processing Infrastructure**
- **Expensive Fault Tolerance Solution**

Munculnya paradigma pemrograman **Object Oriented Programming** dan **Object Store Database** memberikan paradigma baru bagaimana cara melakukan **Scaling Distributed Data Processing** secara efektif pada beberapa mesin komputer sekaligus, semuanya dapat diwujudkan dengan konsep **Effective** **Object Oriented Programming** dan **Non-relational Data Store**.

Karakteristik Arsitektur yang didambakan oleh perusahaan-perusahaan besar di masa itu :

1. Parallel Processing
2. Distributed File based storage
3. Linearly Scalable Infrastructure
4. Programmable API
5. High-speed Replication
6. Fault Tolerance
7. Localized Processing of Data 
8. Localized Storing Data of Result

A simplified approach to large data processing was to create distributed data processing architectures and manage the coordination by programming language techniques.
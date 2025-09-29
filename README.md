# Lab2Web

*Nama    : Amelia Nurmala Dewi*

*NIM     : 312410199*

*Kelas   : TI.24.A2*


## Praktikum 2: CSS Dasar


### 1. Lakukan eksperimen dengan mengubah dan menambah properti dan nilai pada kode CSS
dengan mengacu pada CSS Cheat Sheet yang diberikan pada file terpisah dari modul ini.

Jawab: 
#### Kode CSS Materi Sebelum Perubahan 
```css
nav {
background: #20A759;
color:#fff;
padding: 10px;
}
nav a {
color: #fff;
text-decoration: none;
padding:10px 20px;
}
nav .active,
nav a:hover {
background: #0B6B3A;
}

/* ID Selector */
#intro {
background: #418fb1;
border: 1px solid #099249;
min-height: 100px;
padding: 10px;
}
#intro h1 {
text-align: left;
border: 0;
color: #fff;
}
/* Class Selector */
.button {
padding: 15px 20px;
background: #bebcbd;
color: #fff;
display: inline-block;
margin: 10px;
text-decoration: none;
}
.btn-primary {
background: #E42A42;
}

```
Penjelasan:
- Tampilan awal (materi):
- Navbar berwarna hijau (#20A759).
- Section intro berwarna biru (#418fb1) dengan teks putih.
- Tombol berwarna abu-abu (#bebcbd) dan merah (#E42A42).

hasil tampilan Awal:
<img width="1366" height="768" alt="Screenshot (314)" src="https://github.com/user-attachments/assets/862bc62b-81e0-46dc-9c2e-6d930b17ec81" />

#### Kode CSS Modifikasi (Setelah Perubahan)

```css
body {
  font-family: 'Open Sans', sans-serif;
}

/* Header */
header {
  min-height: 80px;
  border-bottom: 1px solid #77CCEF;
}
h1 {
  font-size: 24px;
  color: #0F189F;
  text-align: center;
  padding: 20px 10px;
}
h1 i {
  color: #6d6a6b;
}

/* Nav */
nav {
  background: #000000; /* hitam pekat */
  color: #fff;
  padding: 20px;
  border-radius: 12px;
}
nav a {
  color: yellow; /* link jadi kuning */
  text-decoration: none;
  padding: 12px 25px;
  font-weight: bold;
  font-size: 18px;
}
nav .active,
nav a:hover {
  background: red; /* hover merah */
  color: white;
}

/* ID Selector */
#intro {
  background: orange;
  border: 3px solid black;
  min-height: 150px;
  padding: 20px;
  box-shadow: 5px 5px 15px rgba(0,0,0,0.6);
}
#intro h1 {
  text-align: center;
  color: blue;
  font-size: 40px;
  text-transform: uppercase;
  letter-spacing: 3px;
  text-shadow: 3px 3px 8px white;
}

/* Class Selector */
.button {
  padding: 10px 20px;       /* kecilin padding */
  background: purple;
  color: white;
  font-size: 16px;          /* font lebih kecil */
  border-radius: 8px;
  text-decoration: none;
  display: inline-block;
  margin-top: 15px;         /* kasih jarak dari paragraf */
}
.btn-primary {
  background: green;
  border: 2px solid yellow;
}

```

Penjelasan:
Tampilan setelah modifikasi:
- Navbar berubah jadi hitam, link kuning, hover merah.
- Section intro berubah jadi oranye dengan border hitam dan efek shadow.
- Heading <h1> di dalam intro lebih besar (40px), berwarna biru, uppercase, dengan efek shadow putih.
- Tombol berubah jadi ungu (class .button) dan hijau (class .btn-primary) dengan border kuning.

hasil tampilan Modifikasi:
<img width="1366" height="768" alt="Screenshot (320)" src="https://github.com/user-attachments/assets/fcb49113-ea6b-4291-99ce-89c77db2f513" />

Kesimpulan:
- Sebelum: sederhana, hanya ada navbar hijau, intro biru, tombol abu-abu/merah.
- Sesudah: tampilan lebih menarik dengan warna kontras, shadow, dan efek hover
### 2. Apa perbedaan pendeklarasian CSS elemen h1 {...} dengan #intro h1 {...}? berikan
penjelasannya!

Jawab :

A. **`h1 { ... }`**
   - Disebut **element selector**.
   - Aturan ini berlaku untuk **semua elemen `<h1>`** di halaman HTML.
   - Pada kode saya:
     ```css
     h1 {
       font-size: 24px;
       color: #0F189F;
       text-align: center;
       padding: 20px 10px;
     }
     ```
   - Contoh HTML:
     ```html
     <header>
       <h1>CSS Internal dan <i>Inline CSS</i></h1>
     </header>
     ```
     ➝ Semua `<h1>` termasuk yang ada di dalam `<header>` akan tampil biru (#0F189F), ukuran 24px, dan rata tengah.

---

B. **`#intro h1 { ... }`**
   - Disebut **ID selector yang lebih spesifik**.
   - Aturannya hanya berlaku untuk elemen `<h1>` yang ada **di dalam elemen dengan `id="intro"`**.
   - Pada kode saya:
     ```css
     #intro h1 {
       text-align: center;
       color: blue;
       font-size: 40px;
       text-transform: uppercase;
       letter-spacing: 3px;
       text-shadow: 3px 3px 8px white;
     }
     ```
   - Contoh HTML:
     ```html
     <div id="intro">
       <h1>Hello World</h1>
       <p>Kami sedang belajar HTML dan CSS dasar...</p>
     </div>
     ```
     ➝ Hanya `<h1>` di dalam `<div id="intro">` yang tampil biru tua, huruf kapital, lebih besar (40px), dan ada efek bayangan.

---

#### Kesimpulan
- `h1 { ... }` = berlaku global untuk semua heading `<h1>` di halaman.  
- `#intro h1 { ... }` = berlaku spesifik hanya untuk `<h1>` di dalam `#intro`.  
- Jika keduanya ada, maka aturan yang lebih spesifik (`#intro h1`) **akan menang**.


### 3. Apabila ada deklarasi CSS secara internal, lalu ditambahkan CSS eksternal dan inline CSS pada
elemen yang sama. Deklarasi manakah yang akan ditampilkan pada browser? Berikan
penjelasan dan contohnya!

Jawab:

A. **Class Selector (`.namaClass`)**
   - Ditulis dengan tanda titik (`.`).
   - Bisa dipakai oleh **banyak elemen** sekaligus (reusable).
   - Pada kode saya, contoh class selector adalah:
     ```css
     .button {
       padding: 10px 20px;
       background: purple;
       color: white;
       font-size: 16px;
       border-radius: 8px;
       text-decoration: none;
       display: inline-block;
       margin-top: 15px;
     }

     .btn-primary {
       background: green;
       border: 2px solid yellow;
     }
     ```
   - Contoh HTML:
     ```html
     <a class="button btn-primary" href="#intro">Informasi selengkapnya.</a>
     ```
     ➝ Elemen `<a>` tersebut akan mendapat style dari **kedua class**: `.button` dan `.btn-primary`.

---

B. **ID Selector (`#namaID`)**
   - Ditulis dengan tanda pagar (`#`).
   - Dipakai hanya untuk **satu elemen unik** dalam halaman HTML.
   - Pada kode saya, contoh ID selector adalah:
     ```css
     #intro {
       background: orange;
       border: 3px solid black;
       min-height: 150px;
       padding: 20px;
       box-shadow: 5px 5px 15px rgba(0,0,0,0.6);
     }

     #intro h1 {
       text-align: center;
       color: blue;
       font-size: 40px;
       text-transform: uppercase;
       letter-spacing: 3px;
       text-shadow: 3px 3px 8px white;
     }
     ```
   - Contoh HTML:
     ```html
     <div id="intro">
       <h1>Hello World</h1>
       <p>Kami sedang belajar HTML dan CSS dasar...</p>
     </div>
     ```
     ➝ Hanya elemen `<div>` dengan `id="intro"` (dan `<h1>` di dalamnya) yang terpengaruh aturan ini.

---

### Kesimpulan
- **Class (`.button`, `.btn-primary`)** → digunakan untuk banyak elemen, bisa dipakai berulang kali.  
- **ID (`#intro`)** → hanya untuk satu elemen unik di dalam halaman.  
- Dalam kode saya, `.button` dan `.btn-primary` dipakai untuk tombol/link, sedangkan `#intro` dipakai untuk mengatur section khusus.

### 4. Pada sebuah elemen HTML terdapat ID dan Class, apabila masing-masing selector tersebut
terdapat deklarasi CSS, maka deklarasi manakah yang akan ditampilkan pada browser?
Berikan penjelasan dan contohnya! ( <p id="paragraf-1" class="text-paragraf">

Contoh elemen:  
```html
<p id="paragraf-1" class="text-paragraf">Ini adalah paragraf percobaan.</p>
```

Jawab: 

Browser menentukan aturan CSS yang dipakai berdasarkan specificity (tingkat kekuatan selector).
Urutan prioritasnya adalah:
- Inline style (style langsung di elemen) → paling kuat.
- ID selector (#id) → lebih spesifik dibanding class.
- Class selector (.class), attribute selector, pseudo-class (:hover, :first-child).
- Tag/elemen selector (p, h1, dll).

Jadi, jika ID dan Class mendeklarasikan properti yang sama, maka aturan ID akan menang.
Jika deklarasinya berbeda, maka keduanya dipakai.

Contoh HTML:
 ```
<p id="paragraf-1" class="text-paragraf">
  Ini adalah paragraf percobaan.
</p>
 ```
Contoh CSS:
 ```
.text-paragraf {
  color: blue;
  font-size: 16px;
}
#paragraf-1 {
  color: red;
}
 ```
Hasil di Browser
- Warna teks: merah (karena ID #paragraf-1 lebih spesifik, menimpa aturan class).
- Ukuran font: 16px (tetap diambil dari class, karena ID tidak mendeklarasikan ukuran font).






# Lab2Web
**Nama: Nadine Amelia Putri**

**Kelas: TI.24.A2**

**Nim: 312410188**

**Mata Kuliah: Pemrograman Web 1**

# Langkah-langkah Praktikum

# 1. Membuat dokumen HTML
<img width="1084" height="327" alt="image" src="https://github.com/user-attachments/assets/1d008a5f-6942-4af5-9469-19802996480f" />


# 2. Mendeklarasikan CSS Internal
<img width="1907" height="428" alt="image" src="https://github.com/user-attachments/assets/76fa2cb2-b75f-4d66-b890-973d5fc6f9bd" />


# 3. Menambahkan Inline CSS
<img width="1099" height="473" alt="image" src="https://github.com/user-attachments/assets/fa8bb751-db35-452a-9f34-2ad07c6c3128" />


# 4. Membuat CSS Eksternal
<img width="1104" height="499" alt="image" src="https://github.com/user-attachments/assets/7fc1c972-2ead-4596-9d33-d7c0cdf31f4f" />



# 5. Menambahkan CSS Selector
<img width="1919" height="579" alt="image" src="https://github.com/user-attachments/assets/e58d55d0-9ab2-4f83-a747-a752b4e0d433" />




# Pertanyaan dan Tugas

**2. Apa perbedaan pendeklarasian CSS elemen h1 {...} dengan #intro h1 {...}? berikan
penjelasannya!**

`h1 { ... }`
Disebut selektor elemen dan berlaku untuk semua elemen `<h1>` di seluruh halaman HTML.
`<h1>` Bersifat umum dan global.

`#intro h1 { ... }`
Disebut selektor turunan dengan id dan berlaku hanya pada elemen `<h1>` yang berada di dalam elemen dengan atribut `id="intro".`
`#intro h1 { ... }` Bersifat lebih spesifik.


**3. Apabila ada deklarasi CSS secara internal, lalu ditambahkan CSS eksternal dan inline CSS pada elemen yang sama. 
Deklarasi manakah yang akan ditampilkan pada browser? Berikan penjelasan dan contohnya!**

Apabila pada elemen yang sama terdapat deklarasi internal CSS, eksternal CSS, dan inline CSS, maka yang akan ditampilkan oleh browser adalah inline CSS. Hal ini terjadi karena CSS memiliki aturan prioritas (CSS Cascade) dengan urutan sebagai berikut:

Hal ini terjadi karena CSS memiliki aturan prioritas (CSS Cascade) dengan urutan sebagai berikut:

- *Eksternal CSS (paling lemah) → aturan pada file .css yang dihubungkan dengan `<link>`.*

contoh:
```
   <link rel="stylesheet" href="style_eksternal.css" type="text/css">
```
  
- *Internal CSS → aturan dalam tag `<style>` di halaman HTML.*

  
contoh:
```
    <style>
        h1 {
            `color: green; /* Internal CSS */
        }
    </style>
```


- *Inline CSS (paling kuat) → aturan langsung pada atribut style di dalam elemen HTML.*

contoh: 
```
   <h1 style="color: red;">CSS Internal dan <i>Inline CSS</i></h1>
```

<img width="1919" height="586" alt="image" src="https://github.com/user-attachments/assets/7e934e25-7d51-4e2f-b4b3-0a627956ecdc" />

Seperti yang dapat dilihat bahwa pada `CSS Internal dan` akan menghasilkan warna merah


Konsekuensi
- Jika ketiga jenis CSS ini mengatur properti yang sama (misalnya warna teks), maka inline CSS akan mengalahkan internal maupun eksternal CSS.

- Jika sebuah elemen memiliki gaya dari ketiga jenis deklarasi CSS tersebut, maka gaya yang ditulis inline akan mengalahkan gaya dari internal maupun eksternal.

- Internal CSS akan mengalahkan eksternal CSS jika keduanya mengatur properti yang sama pada elemen yang sama.

- Eksternal CSS hanya berlaku apabila tidak ditimpa oleh aturan internal atau inline.

- Jika sebuah aturan diberi deklarasi !important, maka aturan itu akan diprioritaskan meskipun berada pada eksternal atau internal CSS.


**4. Pada sebuah elemen HTML terdapat ID dan Class, apabila masing-masing selector tersebut terdapat deklarasi CSS, maka deklarasi manakah yang akan ditampilkan pada browser? Berikan penjelasan dan contohnya! ( <p id="paragraf-1" class="text-paragraf"> )**

**Penjelasan**

*Class Selector*
Selektor dengan tanda titik (.text-paragraf) memiliki tingkat spesifisitas lebih tinggi dibandingkan selektor elemen biasa (p { ... }). Aturan class berlaku pada semua elemen yang memiliki atribut class tertentu.

*ID Selector*
Selektor dengan tanda pagar (#paragraf-1) memiliki tingkat spesifisitas lebih tinggi dibandingkan selektor class. Aturan id hanya berlaku pada satu elemen unik yang memiliki atribut id tertentu.

*Prioritas*
Jika sebuah elemen memiliki id dan class sekaligus, serta keduanya memiliki aturan CSS untuk properti yang sama (misalnya color), maka aturan id (#paragraf-1) akan mengalahkan aturan class (.text-paragraf).

*Kecuali ada !important*
Jika salah satu deklarasi menggunakan !important, maka aturan itu akan diprioritaskan meskipun berasal dari class.

contohnya:
Jika menambahkan code ini pada `.html`
```
 <p id="paragraf-1" class="text-paragraf">
    Ini adalah paragraf dengan ID dan Class.
</p>
```

Dan menggunakan `.css` seperti ini
```
/* Class selector */
.text-paragraf {
    color: blue;
    font-size: 18px;
}

/* ID selector */
#paragraf-1 {
    color: red;
}
```
Akan menghasilkan seperti berikut:
<img width="1040" height="698" alt="image" src="https://github.com/user-attachments/assets/1e7061d2-fac5-4f2c-bad5-fff7e92697df" />
Walaupun, Class `.text-paragraf` → memberi warna biru dan ukuran huruf 18px.

Akan tetapi jika, ID `#paragraf`-1 → memberi warna merah.

Maka teks  "Ini adalah paragraf dengan ID dan Class" #paragraf akan tampil warna merah dengan ukuran huruf 18px.

Kesimpulannya:

Jika sebuah elemen HTML menggunakan ID dan class sekaligus, maka:

- Aturan dari ID selector akan lebih dominan untuk properti yang sama.

- Aturan dari class selector tetap berlaku untuk properti lain yang tidak ditentukan dalam ID.

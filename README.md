# Pengenalan RecyclerView dalam Android

## Pengertian RecyclerView
RecyclerView adalah komponen penting dalam pengembangan aplikasi Android yang digunakan untuk menampilkan data dalam jumlah besar secara efisien. 
Dengan fitur daur ulang tampilan, RecyclerView memungkinkan aplikasi tetap ringan, responsif, dan hemat daya meskipun harus menangani banyak elemen sekaligus. 

## NAMA TIM
1.ANZILUL NUR ROHMA (04)
2.CHYINTA FITRI RAMADHANI (09)
3.IMAM MAULANA MALIK (17)

## FITUR YANG SUDAH ADA:
- DAFTAR DATA DIRI SISWA
- MEMILIH DATA DIRI SISWA LEBIH DARI SATU
- MELIHAT DATA DIRI SISWA
- MENGHAPUS DATA DIRI SISWA
- MENGEDIT DATA DIRI SISWA
- MENAAMBAH DATA DIRI SISWA

## Alur dan Komponen Data
1.Student.kt (Model Data)
• Berisi struktur data siswa (nama, NIS, kelas, dan foto) menggunakan data class.
2.StudentAdapter.kt (Adapter)
• Menjembatani antara data siswa dan tampilan daftar di RecyclerView. Bertugas menampilkan data ke dalam item list.
3.item_student.xml (Tata Letak Item)
• Layout untuk satu item siswa. Menampilkan gambar, nama, NIS, dan kelas siswa.
4.MainActivity.kt
• Menampilkan seluruh daftar siswa menggunakan RecyclerView.
5.DetailActivity.kt
• Menampilkan informasi detail dari siswa yang dipilih.

## Fitur Aplikasi 
• Menampilkan daftar berisi 10 siswa.
• Tampilan daftar disusun secara vertikal menggunakan RecyclerView.
• Masing-masing item memiliki tombol Edit dan Hapus.
• Pengguna bisa menambahkan gambar, nama, NIS, dan kelas siswa.
• Klik pada siswa akan membuka halaman detail siswa menggunakan Intent.


## studentadapter.kt
![1a](https://github.com/user-attachments/assets/d56f3189-cc3d-47dd-91bd-8476b86b99d8)
![2a](https://github.com/user-attachments/assets/7cbf1ec4-834e-4808-a731-6311a9da2e34)
![3a](https://github.com/user-attachments/assets/1d172d9d-c27d-47d2-be6a-e168624c3499)
![4a](https://github.com/user-attachments/assets/b11a8e12-a093-442d-b281-ced5de757217)
![5a](https://github.com/user-attachments/assets/4e646985-46e7-4721-97cc-92dbb3385708)
![6a](https://github.com/user-attachments/assets/7415fa77-eb42-4558-bd18-fd546d3fce89)


1.Adapter & ViewHolder
StudentAdapter digunakan untuk menghubungkan data studentList ke RecyclerView.
ViewHolder menampung tampilan nama, NIS, kelas, dan tombol Edit & Hapus.

2.onBindViewHolder
Menampilkan data siswa ke tampilan TextView, dan memberi aksi saat item diklik (buka detail).

3.filterList(query: String)
Menyaring data berdasarkan nama siswa (fitur pencarian).

4.sortByName()
Mengurutkan data siswa berdasarkan nama.

5.Edit Data (btnEdit)
•Menampilkan dialog edit.
•Setelah disimpan, data diperbarui di list dan RecyclerView di-refresh.

6.Hapus Data (btnDelete)
•Menampilkan dialog konfirmasi.
•Jika ya, data dihapus dan list diperbarui.

## detailactivity.kt
![1b](https://github.com/user-attachments/assets/e291d0d9-9a35-4a7c-b9cb-8df690f231df)

•Program ini dijalankan saat DetailActivity dibuka.
•Data siswa yang dikirim dari layar sebelumnya akan diambil (intent.getStringExtra(...)).
•Data tersebut akan ditampilkan ke 3 kolom teks: Nama, NIS, dan Kelas.

## mainactivity.kt
![1c](https://github.com/user-attachments/assets/e6283766-ce6a-488d-874e-b705eebde396)
![2c](https://github.com/user-attachments/assets/a204c265-d884-4d65-a935-3f3d8f42ef41)
![3c](https://github.com/user-attachments/assets/717a9960-e425-47ba-9fe1-60e7da5a386f)
![4c](https://github.com/user-attachments/assets/82fd3762-e963-4c04-953f-bddc9a7874fb)
![5c](https://github.com/user-attachments/assets/277a26ea-7e21-4344-8e98-b3f116cfad0c)

1. Merupakan activity utama yang menampilkan daftar siswa.  
2. Variabel Utama:
• recyclerView: Menampilkan daftar data siswa
• adapter: Adapter khusus untuk siswa (StudentAdapter)
• studentList: List data siswa
3. Data Siswa (Dummy)
Daftar siswa ditambahkan manual
4. Tampilan RecyclerView
RecyclerView dihubungkan dengan adapter dan layout manager agar data bisa ditampilkan dalam bentuk daftar.
5. Tombol “Tambah”
Tombol btnAdd digunakan untuk membuka popup dialog untuk menambahkan siswa baru.
6. Dialog Tambah Siswa
Saat tombol “Tambah” ditekan:
• Akan muncul dialog input.
• User mengisi nama, nis, dan kelas.
• Jika tidak kosong, data akan ditambahkan ke studentList.
• RecyclerView otomatis diperbarui.
8. Fitur Pencarian
Terdapat EditText bernama searchEditText:
• Saat user mengetik, akan mem-filter isi daftar berdasarkan keyword pencarian.
• Pencarian bekerja secara real-time

## activity_detail.xml
![1d](https://github.com/user-attachments/assets/c90f9da2-b1ea-4ce0-a315-c745d198226e)

Menampilkan halaman detail siswa berupa:
• Judul “Biodata Siswa”
• Foto siswa (icon)
• Informasi siswa:
• Nama
• NIS
• Kelas
Isi Layout 
1. LinearLayout (Root)
• Orientasi: Vertikal
• Padding: 20dp
• ID: @+id/main
• Fungsi: Tempat semua komponen lainnya ditata dari atas ke bawah.
2. TextView (Judul)
Menampilkan teks “Biodata Siswa”
• Teks ditengah, ukuran besar (40sp), warna hitam, tebal
3. ImageView
• Menampilkan gambar ikon siswa (ambil dari drawable)
• Ukuran: 80dp x 80dp
• Letaknya ditengah layout
4. TextView Data Siswa
Ada 3 buah TextView:
a. tvNama
• Menampilkan nama siswa
• Ukuran teks: 20sp
• Teks tebal
b. tvNis
• Menampilkan NIS siswa
• Ukuran teks: 18sp
c. tvKelas
• Menampilkan kelas siswa
• Ukuran teks: 18sp

## activitymain.xml
![1e](https://github.com/user-attachments/assets/9102d353-a577-498c-95ca-e4ae96b9248d)

1. LinearLayout
• Menampung EditText dan Button secara vertikal
• Padding: 16dp
• Lebar: 0 (karena ini dipakai di dalam ConstraintLayout, lebarnya diatur oleh constraint)
• Diatur agar berada di bagian atas halaman
2.EditText
Kolom pencarian siswa
• Hint (teks samar): “Cari siswa…”
• Ada icon search di sebelah kiri (drawableStart)
3. Button
• Tombol untuk membuka dialog Tambah Siswa
• Diletakkan di bawah RecyclerView
•  Margin atas 16dp supaya tidak menempel langsung

## dialog_add_student.xml
![1f](https://github.com/user-attachments/assets/29cb9850-c0dd-4b9c-b071-940a39141ce6)

- Dialog Tambah Siswa
Layout ini digunakan untuk form input saat ingin menambahkan data siswa baru.
-Terdapat 3 Kolom Isian:
1.Nama 
Kolom untuk mengetik nama siswa.
2.NIS
Kolom untuk mengetik Nomor Induk Siswa.
3.Kelas
Kolom untuk mengetik kelas siswa.
-Fungsi Utama Layout Ini
Layout ini dipakai di dalam dialog popup yang muncul saat tombol “Tambah Siswa” ditekan.
Isian dari ketiga kolom ini akan digunakan untuk menambahkan data baru ke daftar siswa.

## dialog_edit.xml
![1g](https://github.com/user-attachments/assets/7ab15c6d-6a56-4649-8287-1ec301b43b96)

-Isi Form:
1.Input Nama
• Untuk memasukkan nama siswa.
• Ada label bantu (hint) bertuliskan “Nama”.
2. Input NIS
• Untuk memasukkan Nomor Induk Siswa.
• Ada hint “NIS”.
3. Input Kelas
• Untuk memasukkan kelas siswa.
• Ada hint “Kelas”.

-Tampilan Layout:
• Semua komponen ditata secara vertikal (dari atas ke bawah).
• Memiliki padding 16dp agar tidak terlalu menempel ke tepi layar.
• Lebar komponen mengikuti layar penuh (match_parent).

## item_student.xml
![1j](https://github.com/user-attachments/assets/67f5a6f7-66e4-42b1-bf5a-ed28517fd53c)
![2j](https://github.com/user-attachments/assets/bba074e1-3ec0-4dac-8911-839f274b0725)


1.Gambar/Foto Siswa
• Terletak di sebelah kiri dengan ukuran kecil (48dp).
• Gambar diambil dari folder drawable.
2.Teks Keterangan (Kemungkinan Nama/NIS/Kelas)
• Ditata secara vertikal di samping foto.
• Teks ini berada di tengah antara foto dan tombol.
3. Dua Tombol Aksi (Edit & Hapus)
• Terletak di paling kanan.
• Menggunakan ikon, tidak ada teks, hanya gambar tombol edit dan hapus.
- Tombol Edit dan Hapus
Bagian ini adalah subbagian dari layout di atas yang menjelaskan:
Dua ImageButton:
-Tombol Edit: berisi ikon pensil (edit).
-Tombol Hapus: berisi ikon tempat sampah (delete).
-Keduanya memiliki latar belakang transparan, jadi hanya ikon yang terlihat.
-Tombol ini ditata secara horizontal (berdampingan).

## KESIMPULAN
Aplikasi ini menampilkan dan mengelola data siswa menggunakan RecyclerView secara efisien. Pengguna dapat melihat, menambah, mengedit, menghapus, dan mencari siswa dengan mudah. Data siswa ditampilkan dalam daftar vertikal, setiap item berisi foto, nama, NIS, kelas, serta tombol edit & hapus. Arsitektur aplikasi terdiri dari model data, adapter, layout item, dan dua activity utama: MainActivity (daftar) dan DetailActivity (detail siswa). Dialog digunakan untuk input dan edit data.
















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
1.	Student.kt (Model Data)
	•	Berisi struktur data siswa (nama, NIS, kelas, dan foto) menggunakan data class.
2.	StudentAdapter.kt (Adapter)
	•	Menjembatani antara data siswa dan tampilan daftar di RecyclerView. Bertugas menampilkan data ke dalam item list.
3.	item_student.xml (Tata Letak Item)
	•	Layout untuk satu item siswa. Menampilkan gambar, nama, NIS, dan kelas siswa.
4.	MainActivity.kt
	•	Menampilkan seluruh daftar siswa menggunakan RecyclerView.
5.	DetailActivity.kt
	•	Menampilkan informasi detail dari siswa yang dipilih.

## Fitur Aplikasi 
	•	Menampilkan daftar berisi 10 siswa.
	•	Tampilan daftar disusun secara vertikal menggunakan RecyclerView.
	•	Masing-masing item memiliki tombol Edit dan Hapus.
	•	Pengguna bisa menambahkan gambar, nama, NIS, dan kelas siswa.
	•	Klik pada siswa akan membuka halaman detail siswa menggunakan Intent.




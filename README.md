# SIG_Sampling-Raster-Data-using-Points-or-Polygons

*Tutorial Sampling Raster Data using Points or Polygons

1. Download terlebih dahulu file us.tmax_nohads_ll_20190501.tif, 2018_Gaz_ua_country.zip, dan tl_2018_us_country.zip 

2. Buka QGIS terlebih dahulu dan buka file baru. Buka zip dan ekstrak 2018_Gaz_ua_national.zip dan tl_2018_us_county.zip. Pilih file us.tmax_nohads_ll_20190501_float.tif pada browser lalu seret ke kanvas (*Gambar 1*)

3. Kita akan melihat layer raster baru us.tmax_nohads_ll_20190501_float dimuat di panel layers. Lapisan raster ini berisi suhu maksimum yang tercatat pada setiap pixel dalam derajat Celcius. Selanjutnya kita akan membuat file titi area perkotaan. File ini hadir sebagai file teks dalam format Tab Separated Values (TSV). Klik Open Data Source Manager pada toolbar (*Gambar 2*)

4. Beralih ke tab Delimited Text. Klik tombol ... di sebelah File name dan tentukan jalur ke file teks yang kita unduh. Pada bagian File format, pilih Custom delimiters dan centang tab. Pilin INTPTLONG sebagai bidang x dan INTPTLAT sebagai bidang Y. Lalu klik Add (*Gambar 3*)

5. Lapisan titik baru 2018_Gaz_ua_national akan dimmuat di panel layer. Sekarang kita siap untuk mengestrak nilai dari lapisan raster pada titik-titik ini. Pilih Processing lalu klik Toolbox (*Gambar 4*)

6. Cari dan temukan Raster analysis lalu pilih Sample raster values. Klik dua kali untuk menampilkannya (*Gambar 5*)

7. Pilih 2018_Gaz_ua_national sebagai lapisan titik input. Pilih us.tmax_nohads_ll_20190501_float sebagai lapisan Raster untuk dijadikan sampel. Luaskan parameter lanjutan dan masukkan tmax sebagai awalan kolom keluaran. Klik Run (*Gambar 6*)

8. Layer baru Sampled akan dimuat pada panel layers. Pilih Identify tool pada attributes toolbar dan klik dimana saja. Kita akan melihat atribut ditampilkan di panel Identifikasi hasil. Kita akan melihat atribut baru bernama tmax_1 ditambhakan ke setiap fitur. Ini adalah nilai pixel dari lapisan raster yang diwkstraksi di lokasi titik. Angka 1 mewakili nomor pita raster. Jika lapisan raster memiliki banyak pita, kita akan melihat banyak kolom baru di lapisan keluaran (*Gambar 7*)

9. Bagian pertama dari analisis selesai. Kitas hapus lapisan yang tidak perlu. Tahan tombol shift dan pilih sampled dan 2018_Gaz_national. Klik kanan dan pilih Remove layer. Saat diminta untuk hapus 2 entri legenda pilih OK (*Gambabr 8*)

10. Sekarang kita akan menggunakan lapisan kabupaten untuk mengambil sampel raster dan menghitung suhu rata-rata untuk setiap kabupaten. Temukan file tl_2018_us_county.shp pada browaer QGIS, seret ke kanvas (*Gambar 9*)

11. Layer baru tl_2018_us_county akan dimuat ke panel layer. Pilih Procesing lalu klik Toolbox (*Gambar 10*)

12. Cari dan temukan Raster analysisi dan pilih Zonal statstics lalu klik dua kali untuk menampilkannya (*Gambar 11*)

13. Pilih us.tmax_nohads_ll_20190501_float sebagai layer Raster dan tl_2018_us_cpunty sebagai layer Vector yang berisi zona. Masukkan tmax_ sebagai awalan kolom keluaran. Klik ... di samping Statistics untuk menghitung (*Gambar 12*)

14. Pilih hanya nilai Mean dan klik OK (*Gambar 13*)

15. Kita jalankan untuk memulai pemrosesan. Algoritme mungkin membutuhkan waktu beberapa menit untuk selesai (*Gambar 14*)

16. Klik kanan layer Zonal Statistics (*Gambar 15*)

17. Kita akan melihat kolom baru bernama tamx_mean ditambahkan ke tabel atribut. Inin berisi nilai suhu rata-rata yang diekstrasksi di atas poligon untuk setiap fitur. Ada beberapa nilai nol karena kabupaten tersebut milik Alaska, Hawaii, dan Puerto Riko berada di luar jangkauan lapisan raster (*Gambar 16* *Gambar 17*)

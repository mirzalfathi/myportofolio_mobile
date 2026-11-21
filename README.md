Nama : Mirza
NPM : 2506618572
Kelas : PBP A

## Deskripsi
Website portofolio mobile pribadi Mirza Al Fathi, dibuat untuk menampilkan profil, riwayat pendidikan, pengalaman, dan lainnya. Proyek ini dibuat sebagai bagian dari tugas mata kuliah pemrograman berbasis platform menggunakan Flutter.

---

### Tugas 7
1. Widget tree adalah struktur berbentuk pohon yang tersusun dari seluruh widget dalam aplikasi Flutter, mulai dari widget paling atas (root) sampai widget paling dalam. Setiap elemen di layar, seperti teks, tombol, jarak, dan tata letak, merupakan widget. Dalam hubungan parent-child, widget parent membungkus widget child dan mengatur ruang yang boleh digunakan child serta posisinya. Widget dengan satu anak memakai properti child (contoh: Center, Padding), sedangkan widget dengan banyak anak memakai properti children (contoh: Column, Row). Ketika sebuah widget dibangun ulang, seluruh widget di bawahnya ikut dibangun ulang.2.
2. - MaterialApp: root aplikasi, mengatur judul, tema, dan halaman awal (home)
   - MyApp, MyHomePage, InfoCard, ItemCard: widget buatan sendiri bertipe StatelessWidget
   - Scaffold: kerangka dasar halaman
   - AppBar: bilah judul “MyPortfolio” di bagian atas
   - Padding: memberi jarak di sekeliling konten
   - Column: menyusun widget secara vertikal
   - Row: menyusun tiga InfoCard secara horizontal
   - SizedBox: memberi jarak kosong antarwidget
   - Center: menempatkan konten di tengah
   - Text: menampilkan teks (judul, NPM, nama, kelas, pesan sambutan)
   - GridView.count: menampilkan tombol menu dalam kisi tiga kolom
   - Card: kartu berbayang pada InfoCard
   - Container: wadah yang mengatur lebar (memakai MediaQuery) dan padding
   - Material: memberi warna dan sudut membulat pada ItemCard
   - InkWell: mendeteksi tekanan (onTap) dan menampilkan efek ripple
   - Icon: menampilkan ikon pada tiap tombol
   - SnackBar: pesan singkat yang muncul lewat ScaffoldMessenger saat tombol ditekan
3. MaterialApp adalah widget yang menyediakan konfigurasi dasar untuk aplikasi bergaya Material Design, seperti tema warna dan tipografi, navigasi antarhalaman, dan lainnya. Widget ini umumnya dijadikan root karena banyak widget Material lain, seperti Scaffold, AppBar, dan SnackBar, membutuhkan informasi dari konfigurasi tersebut agar dapat berfungsi. Dengan meletakkannya di paling atas widget tree, seluruh widget di bawahnya otomatis dapat menggunakan tema dan navigasi yang sama.
4. StatelessWidget adalah widget yang tampilannya tidak berubah setelah dibuat karena hanya bergantung pada data yang diterimanya dari luar, sedangkan StatefulWidget memiliki state internal sehingga tampilannya dapat berubah selama aplikasi berjalan melalui pemanggilan setState(). StatelessWidget sebaiknya dipilih untuk tampilan yang bersifat tetap, seperti judul, ikon, atau kartu informasi. StatefulWidget digunakan ketika tampilan perlu berubah akibat interaksi pengguna atau perubahan data, misalnya input form, atau tombol on/off.
5. BuildContext adalah referensi lokasi sebuah widget di dalam widget tree. Lewat context, widget bisa mengambil informasi dari widget di atasnya, seperti Theme.of(context) untuk warna di AppBar dan MediaQuery.of(context) untuk lebar InfoCard. Di method build(BuildContext context), context tersedia sebagai parameter dan dipakai untuk mengakses informasi tersebut saat menyusun tampilan.
6. Hot reload menerapkan perubahan kode ke aplikasi yang sedang berjalan tanpa menghilangkan data atau halaman yang sedang dibuka. Hot restart menjalankan ulang aplikasi dari awal sehingga semuanya kembali ke kondisi awal. Hot reload tidak cukup kalau yang diubah adalah nilai awal variabel (misalnya nama di MyHomePage), jadi perlu hot restart. Kalau menambah package, asset, atau mengubah pengaturan Android/iOS, aplikasi harus dihentikan lalu dijalankan ulang (full restart).

### Tugas 8
1. Kalau pakai push(), halaman baru ditaruh di atas stack dan halaman lama tetap ada, jadi pengguna masih bisa balik lewat tombol Back. pushReplacement() beda lagi: yang diganti cuma halaman paling atas, sedangkan isi stack di bawahnya tidak berubah. Lalu pop() dipakai untuk menutup halaman atau dialog yang paling atas. Di halaman utama, kartu aksi memakai push() supaya pengguna bisa kembali ke menu dengan tombol Back sistem. Untuk Home di drawer, onTap memanggil pushReplacement() dengan MaterialPageRoute yang membangun MyHomePage(). Jadi halaman yang sedang tampil langsung digantikan halaman utama, dan stack tidak makin menumpuk tiap kali Home ditekan.
2. Scaffold, AppBar, dan Drawer bikin tampilan tiap halaman seragam, mulai dari kerangka, bilah judul, sampai menu sampingnya. Drawer-nya sendiri hanya satu widget, LeftDrawer, yang dipakai ulang lewat drawer: const LeftDrawer(). Jadi kalau menunya mau diubah, cukup edit di satu tempat dan semua halaman ikut berubah. Untuk contoh warna, Colors.indigo dipakai di AppBar pada project_form.dart dan education_form.dart, juga di DrawerHeader pada left_drawer.dart. Cek dulu apakah colorScheme.primary di main.dart memang indigo. Kalau iya, tampilannya konsisten dengan menu.dart
3. Form disusun vertikal pakai Column, bukan Row, karena field memang diisi berurutan dari atas ke bawah, dan Padding dipakai untuk memberi jarak antar-input. Masalahnya, Column tidak bisa di-scroll secara default. Di layar yang sempit atau saat keyboard muncul, kontennya bisa melebihi layar dan memicu RenderFlex overflow. Itu sebabnya SingleChildScrollView benar-benar dibutuhkan, bukan sekadar pelengkap.
4. GlobalKey<FormState> dipakai untuk mengontrol status form dari luar. Tiap validator memeriksa isi field-nya dan mengembalikan null kalau isinya valid, atau String berisi pesan error yang muncul di bawah field. Saat tombol Simpan ditekan, validate() menjalankan semua validator sekaligus, dan kalau hasilnya false, dialog atau proses simpan tidak dijalankan.

---
## AI Disclosure
1. Tugas 7 - Menggunakan Claude untuk membantu menjawab pertanyaan reflektif (https://claude.ai/share/7802b538-9a6b-4975-8f81-01c4517f39cc)
2. Tugas 8 - Menggunakan Claude untuk membantu memperbaiki error navigasi, menyusun struktur form baru (education_form.dart), serta pengecekan checklist tugas. (https://claude.ai/share/4fac8ac4-f869-4e7b-aeac-4523daba66dd, )
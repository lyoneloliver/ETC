
# 1. Deskripsi dan Ruang Lingkup Fitur

ETC Desktop (Elite TC Champions) adalah aplikasi desktop rich UI yang membantu mahasiswa membentuk tim untuk lomba atau proyek. Lewat aplikasi ini, mahasiswa bisa mencari anggota tim, melamar ke rekrutmen milik mahasiswa lain, dan menemukan mentor sesuai keahlian. Satu akun bisa dipakai untuk dua peran sekaligus: sebagai perekrut yang membuka posisi dan sebagai pelamar yang bergabung ke tim lain.

Aplikasi dibangun dengan C#, .NET 10, dan Avalonia UI (Fluent theme), sehingga berjalan di Ubuntu maupun Windows. Polanya MVVM: View menangani tampilan, ViewModel menangani state dan command (CommunityToolkit.Mvvm), Service menangani aturan bisnis, dan Infrastructure menangani SQL Server lewat ADO.NET (Microsoft.Data.SqlClient).

Ruang lingkup fiturnya terbagi menjadi delapan modul:

1. **Akun:** registrasi, login, dan logout. Password wajib 12–128 karakter.
2. **Profil mahasiswa:** foto (PNG/JPEG, maksimal 2 MiB), nama, angkatan, bio, skill, pengalaman, dan tautan portofolio.
3. **Dashboard:** statistik pribadi, yaitu rekrutmen aktif, lamaran menunggu, lamaran diterima, dan bookmark, ditambah ringkasan lamaran terbaru dan rekrutmen milik pengguna.
4. **Cari rekrutmen:** pencarian judul atau kegiatan, filter kategori/skill/posisi, dan pagination. Setiap kartu menampilkan posisi, kuota, sisa tempat, dan tenggat.
5. **Rekrutmen saya:** membuat, mengedit, memublikasikan, dan menutup rekrutmen, lengkap dengan posisi, kuota, kategori lomba/proyek, jadwal, biaya, dan kontak. Pemilik juga dapat melihat daftar pelamar.
6. **Lamaran saya:** mengajukan dan membatalkan lamaran serta memantau hasil seleksi. Pemilik rekrutmen dapat menerima atau menolak pelamar.
7. **Bookmark:** menyimpan rekrutmen yang menarik, termasuk yang sudah ditutup.
8. **Mentor:** direktori mentor yang bisa dicari berdasarkan nama atau keahlian, dengan profil, bidang, prestasi, dan tautan Google Form untuk mentoring.

Di balik semua modul itu ada validasi input, pembatasan akses sesuai pemilik data, validasi kuota, dan penyimpanan persisten di SQL Server dengan schema serta data demo.

# 2. Latar Belakang dan Manfaat

## Latar Belakang

Informasi rekrutmen tim lomba dan proyek di kalangan mahasiswa biasanya tersebar di grup chat, media sosial, atau dari mulut ke mulut. Akibatnya, beberapa masalah muncul:

- Perekrut sulit menemukan orang dengan skill yang tepat.
- Mahasiswa yang ingin bergabung sering ketinggalan informasi.
- Proses lamar dan seleksi tidak tercatat, sehingga sisa kuota sulit dipantau.
- Mahasiswa yang butuh bimbingan tidak tahu harus menghubungi mentor yang mana.

ETC dibuat untuk memusatkan semua itu dalam satu aplikasi yang terstruktur.

## Manfaat

1. **Tim lebih cepat terbentuk.** Perekrut dan pelamar bertemu di satu tempat, lengkap dengan pencarian dan filter.
2. **Anggota lebih tepat sasaran.** Posisi dan skill tercatat jelas, sehingga kebutuhan tim cocok dengan kemampuan pelamar.
3. **Proses transparan.** Status lamaran (menunggu, diterima, ditolak) dan sisa kuota terlihat oleh kedua pihak.
4. **Akses ke mentor.** Mahasiswa bisa menemukan mentor berpengalaman sesuai bidang lomba.
5. **Portofolio terkumpul.** Profil memuat skill, pengalaman, dan karya, sehingga menjadi "CV mini" saat melamar.
6. **Data aman dan konsisten.** Ada validasi, kontrol kepemilikan data, dan penyimpanan di database relasional.





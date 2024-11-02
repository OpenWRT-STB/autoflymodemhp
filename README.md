# Konfigurasi Flymode di OpenWRT

Panduan ini menjelaskan langkah-langkah untuk meng-upload dan menjalankan skrip `flymode` di OpenWRT.

## Prasyarat

- Memiliki perangkat OpenWRT baik router atau STB.
- Sumber internet hanya untuk modem HP yang sudah Auto ADB.
- File `flymode` yang sudah siap di-upload.
- Aplikasi SCP atau FTP untuk transfer file.
- Bisa juga upload langsung melalui web ui OpenWRT.

## Langkah-langkah

1. **Upload File ke OpenWRT**
   - Upload file `flymode` ke direktori `/usr/bin` di OpenWRT.

2. **Set Permission**
   - Buka terminal dan jalankan perintah berikut untuk memberikan hak eksekusi pada file:
     ```bash
     chmod +x /usr/bin/flymode
     ```

3. **Test Program**
   - Ketik perintah berikut di terminal untuk melihat apakah jalan atau error `flymode`:
     ```bash
     flymode
     ```

4. **Periksa Error**
   - Jika terdapat error, screenshot pesan error dan kirim ke [WhatsApp](https://wa.me/+62881011068651). 
   - Jika tidak ada error dan muncul pemeriksaan jaringan, lanjut ke langkah berikutnya.

5. **Masuk ke Local Startup**
   - Akses menu `System > Startup > Local Startup` di antarmuka web OpenWRT.

6. **Tambahkan Perintah**
   - Di Local Startup biasanya terdapat perintah:
     ```bash
     sleep 3
     /usr/bin/bled -r
     ```

7. **Tambahkan Baris Berikut**
   - Setelahnya, tambahkan:
     ```bash
     sleep 3
     /usr/bin/bled -r
     sleep 3 &&
     flymode &&
     ```

8. **Simpan dan Terapkan**
   - Simpan perubahan dan reboot perangkat.
   - Scriptnya akan berjalan auto di layar belakang.

## Catatan

Pastikan untuk memeriksa semua langkah dengan seksama. Jika Anda mengalami masalah, jangan ragu untuk menghubungi support.


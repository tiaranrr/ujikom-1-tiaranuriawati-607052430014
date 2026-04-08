Dokumentasi Ujikom 1 Jaringan telekomunikasi

1. Langkah Konfigurasi Asterisk pada Ubuntu
- Masukan kode ini untuk install apt asterisk
  sudo apt install asterisk -y
- Setelah itu masuk ke directory berikut :
  sudo nano /etc/asterisk/sip.conf
- Pada directory tersebut tambahkan kode dibawah ini dibawah kode bawaan :
  [0014]
  type=friend
  host=dynamic
  secret=1234
  context=internal

  [1001]
  type=friend
  host=dynamic
  secret=1234
  context=internal

- Selanjutnya, masuk ke directory berikutnya :
  sudo nano /etc/asterisk/extensions.conf
- Pada directory tersebut, tambahkan kode berikut dibawah kode bawaan :
  [internal]
  exten => 0014,1,Dial(SIP/0014)
  exten => 1001,1,Dial(SIP/1001)

- Berikut kode untuk mendapatkan ip yang digunakan
  ip a
- Setelah mendapat ip, lakukan pengujian pada zoiper

2. Pengujian pada Zoiper
- Pada zoiper laptop tambahkan username 1001 dengan password 1234
- Pada zoiper hp tambahkan username 0014 dengan secret 1234 dan Authentication username tiara nuriawati
- Setelah itu lakukan dial dari hp menuju laptop

3. Berikut adalah hasil pengujian pada zoiper

<img width="1366" height="768" alt="Screenshot (1128)" src="https://github.com/user-attachments/assets/994ac481-fe5e-4d7d-a11b-994c03b82a4e" />

   

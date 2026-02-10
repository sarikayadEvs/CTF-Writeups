🚩 CTF Write-up: picoCTF - Information
Kategori: Forensics

Zorluk: Kolay

Hedef: Verilen görsel dosyasının içine gizlenmiş bayrağı (flag) bulmak.

1. Başlangıç Analizi
Bize verilen dosya cat.jpg isminde bir görsel dosyasıydı. Sorunun açıklamasında yer alan "Files can always be changed in a secret way" (Dosyalar her zaman gizli yollarla değiştirilebilir) ifadesi, dosyanın Metadata (üstveri) kısmına veya dosya yapısının içine bir şeyler gömüldüğüne dair güçlü bir ipucuydu.

2. Keşif (Enumeration)
İlk olarak dosyanın meta verilerini incelemek için exiftool aracını kullandık:

Bash
exiftool cat.jpg
Dikkat Çeken Bulgular:

Copyright Notice: PicoCTF

License: cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9

License alanındaki karakter dizisi, Base64 formatında kodlanmış gibi görünüyordu. Özellikle cGlj ile başlaması, CTF dünyasında çok yaygın bir durumdur; çünkü bu karakterler "pico" kelimesinin Base64 karşılığıdır.

3. Çözüm (Exploitation)
Bulduğumuz Base64 dizisini terminal üzerinden decode (çözme) işlemine tabi tuttuk:

Bash
echo "cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9" | base64 -d
İşlem Sonucu: Kod çözüldüğünde karşımıza çıkan metin: picoCTF{the_m3tadata_1s_modified}

4. Sonuç
Flag: picoCTF{the_m3tadata_1s_modified}

Kullanılan Araçlar: exiftool, base64

Öğrenilen Teknikler: Dijital adli tıpta (Forensics) metadata analizinin önemi ve Base64 kodlamasının tanınması.

🚩 Logs Forensics Analysis
Kategori: Forensics Zorluk: Orta

📝 Problem Analizi
Siber güvenlik ekibi tarafından iletilen devasa boyutlardaki bir log dosyası incelendiğinde, standart kayıtlar yerine yoğun bir kodlanmış metin bloğu tespit edildi. Bu verinin bir dosya taşıdığı şüphesiyle analiz başlatıldı.

🛠️ Çözüm Adımları
Veri Tanımlama: Log dosyasındaki karakter dizisinin iVBORw0KGgo... ile başladığı görüldü. Bu imza, verinin Base64 ile kodlanmış bir PNG görseli olduğunu doğruladı.

Dosya Çıkarma: Metin bloğu base64 -d logs.txt > gizli_dosya.png komutuyla deşifre edilerek görsel formuna geri döndürüldü.

İpucu Tespiti: Oluşturulan görselin alt kısmında, insan gözüyle okunabilen ancak makine dilinde gizlenmiş bir Hexadecimal (Onaltılık) dizi bulundu.

Deşifre Süreci: Tespit edilen Hex dizisi, ASCII karakter tablosu kullanılarak metne dönüştürüldü ve gizli bayrak formatına ulaşıldı.

🏁 Flag
picoCTF{forensics_analysis_is_amazing_2561a194}

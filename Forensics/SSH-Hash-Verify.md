# 🚩 SSH & Hash Verification
**Kategori:** Forensics / Integrity Check
**Zorluk:** Kolay

## 📝 Problem Analizi
Bir sunucuya yapılan SSH bağlantısının güvenilirliğini doğrulamak ve sızdırılan bir dosyanın bütünlüğünü kontrol etmekle görevlendirildik.

## 🛠️ Çözüm Adımları
1. Sunucuya SSH üzerinden güvenli bağlantı sağlandı.
2. Dosya bütünlüğü için `sha256sum` komutu çalıştırıldı.
3. Elde edilen hash değeri, orijinal değerle karşılaştırılarak dosyanın manipüle edilmediği doğrulandı.

## 🏁 Flag
`CTF{s3cur3_shh_v3r1f1cat10n_2026}`

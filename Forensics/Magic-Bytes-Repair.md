# 🚩 Magic Bytes Repair
**Kategori:** Forensics / File Recovery
**Zorluk:** Orta

## 📝 Problem Analizi
Açılmayan bir PNG dosyasının başlık bilgilerinin (header) bozulduğu tespit edildi.

## 🛠️ Çözüm Adımları
1. Dosya bir Hex Editor ile incelendi.
2. İlk baytların standart PNG imzası yerine hatalı veriler içerdiği görüldü.
3. Manuel olarak doğru Magic Bytes değerleri girilerek dosya onarıldı.

## 🏁 Flag
`CTF{h3x_m4g1c_byt3s_f1x3d}`

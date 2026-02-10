# 🚩 Linux Penguin (MT19937 Attack)
**Kategori:** Cryptography / PRNG
**Zorluk:** Zor

## 📝 Problem Analizi
`penguin.py` dosyasındaki şifreleme mekanizmasının tahmin edilebilir bir rastgele sayı üreteci kullandığı görüldü.

## 🛠️ Çözüm Adımları
1. Üretilen 624 adet rastgele sayı verisi toplandı.
2. PRNG durumu (state) yeniden oluşturularak sonraki anahtar tahmin edildi.
3. Şifreli dosya bu anahtar ile deşifre edildi.

## 🏁 Flag
`CTF{mt19937_prng_predictability_88}`

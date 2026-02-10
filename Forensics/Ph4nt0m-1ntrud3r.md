# 🚩 Ph4nt0m 1ntrud3r - PCAP Analysis

**Kategori:** Forensics / Network Analysis
**Zorluk:** Orta

## 📝 Problem Analizi
Bu görevde tarafımıza şüpheli bir ağ trafiği kaydı (PCAP dosyası) iletildi. Hedef, saldırganın sızdırdığı gizli veriyi trafik içerisinden ayıklamaktı.

## 🛠️ Çözüm Adımları
1. **Trafik Gözlemi:** Wireshark kullanarak paketleri incelediğimde, alışılmadık HTTP paketleri tespit ettim.
2. **Filtreleme:** `http.request.method == "POST"` filtresi ile saldırganın dışarı veri gönderdiği paketlere odaklandım.
3. **Veri Ayıklama:** Paketlerin "User-Agent" kısmına gizlenmiş anlamsız karakter dizileri fark ettim. Bunların Base64 parçaları olduğu anlaşıldı.
4. **Decoding:** Tüm parçaları birleştirip Base64 decode işlemi uyguladığımda flag ortaya çıktı.

## 🏁 Flag
`CTF{n3tw0rk_f0r3ns1cs_is_fun_2026}`

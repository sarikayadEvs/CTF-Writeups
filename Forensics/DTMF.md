0xfun CTF: Multi-Layered Signal Analysis
Kategori: Forensics / Crypto

Zorluk: Orta

Dosya Adı: message.wav & image.png

📝 Soru İçeriği
"A series of encoded messages awaits. Analyze the signals and uncover what’s hidden within."
(Kodlanmış bir mesaj serisi sizi bekliyor. Sinyalleri analiz edin ve içinde neyin saklı olduğunu ortaya çıkarın.)

🔍 1. İlk Analiz (Keşif)
Soruda bize bir ses dosyası (message.wav) ve elektronik bir devre kartı görseli (image.png) verildi. Görseldeki kartın üzerindeki #, * sembolleri ve devre tasarımı, bunun bir DTMF (Dual-Tone Multi-Frequency) sinyal işleme sorusu olduğunu kesinleştirdi.

Bulgu: Ses dosyası doğrudan bir metin değil, frekanslar içine gömülmüş çok katmanlı bir veri içeriyor.

🎧 2. Sinyal İşleme ve Binary Elde Edilmesi
Ses dosyasındaki "bip" seslerini analiz etmek için dijital bir dekoder kullanıldı. Ancak bu soruda DTMF tonları doğrudan rakamları değil, bir binary (ikili) diziyi temsil ediyordu.

İşlem: message.wav dosyası bir DTMF Decoder aracına yüklendi ve sinyaller 0-1 dizisine dönüştürüldü.

Sonuç: 01001101010010000100101001110100... şeklinde uzun bir binary çıktı elde edildi.

📦 3. Veri Dönüştürme (Binary -> Base64)
Elde edilen binary dizisi, 8-bitlik karakter setlerine (ASCII) çevrildiğinde bir Base64 dizgisi olduğu anlaşıldı.

İşlem: İkili sayı dizisi ASCII formatına decode edildi.

Sonuç: MHJtZ2p7VHUxbTFfRjRoX2lzYzVmdm50cn0=

🔐 4. Kriptografik Analiz (Base64 -> ROT13)
Base64 deşifre edildiğinde ortaya çıkan metin, beklenen flag formatına (0xfun{...}) benziyordu ancak karakterler hala anlamlı değildi.

İşlem: Base64 deşifresi sonucu orjgp{Tu1m1_F4h_isc5fvntr} metni elde edildi.

Analiz: orjgp kelimesi ile 0xfun karşılaştırıldığında, harflerin alfabede 13 birim kaydırıldığı (ROT13) tespit edildi.

🏁 5. Birleştirme ve Final (Flag)
Tüm katmanlar (Sinyal -> Binary -> Base64 -> ROT13) sırasıyla çözüldüğünde, hem kullanılan yöntemlere atıfta bulunan hem de anlamlı olan bayrağa ulaşıldı.

Full Flag: 0xfun{Mu1t1_t4p_plu5_dtmf}

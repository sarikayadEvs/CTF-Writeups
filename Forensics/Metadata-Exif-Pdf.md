Secret of the Polyglot
Kategori: Forensics / Polyglots

Zorluk: Kolay/Orta

Dosya Adı: flag2of2-final.pdf

🔍 1. İlk Analiz (Keşif)
Dosyayı aldığımızda uzantısı .pdf olmasına rağmen, sistemler bazen dosya türü konusunda çelişkili bilgiler verebilir. İlk adım olarak dosyanın "magic bytes" (sihirli baytlar) değerlerini kontrol ettik.

Komut: exiftool flag2of2-final.pdf

Bulgu: ExifTool, dosyanın aslında bir PNG olduğunu raporladı. Ancak dosyanın sonunda "Trailer data after PNG IEND chunk" uyarısı verdi. Bu, PNG verisi bittikten sonra dosyanın içinde başka verilerin de saklandığına dair kesin bir kanıttı.

🖼️ 2. Birinci Parçanın Elde Edilmesi (PNG)
Dosyanın başında PNG imzası bulunduğu için, uzantıyı .png yaparak dosyayı bir resim olarak açtık.

İşlem: mv flag2of2-final.pdf flag_part1.png

Sonuç: 50x50 boyutundaki resim dosyasının içinde bayrağın ilk yarısı görsel olarak mevcuttu:

picoCTF{f1u3n7_

📄 3. İkinci Parçanın Elde Edilmesi (PDF)
Dosyanın uzantısı orijinalinde .pdf olduğu için ve ExifTool'un uyarısı dosyanın sonunda ek veri olduğunu belirttiği için, bu sefer dosyayı bir PDF okuyucu ile (veya strings komutuyla) analiz ettik.

İşlem: Dosyayı tarayıcıda veya PDF okuyucuda açtık.

Sonuç: PDF içeriğinde gizlenmiş olan metin bloğunda bayrağın ikinci yarısını bulduk:

1n_pn9_&_pdf_249d05c0}

🏁 4. Birleştirme (Final)
İki farklı "perspektiften" bakılarak elde edilen parçalar birleştirildi:

Part 1: picoCTF{f1u3n7_

Part 2: 1n_pn9_&_pdf_249d05c0}

Full Flag: picoCTF{f1u3n7_1n_pn9_&_pdf_249d05c0}


<img width="499" height="397" alt="image" src="https://github.com/user-attachments/assets/e064ea1c-9c56-4aea-af56-719d4ce9c1fa" />

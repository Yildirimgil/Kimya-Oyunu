# Kimya Laboratuvarı — Kavram Yanılgısı Teşhis Motoru

9-12. sınıf kimya müfredatına (Maarif Modeli) ve olimpiyat seviyesine dayalı bir test/oyun. Amacı yalnızca doğru-yanlış saymak değil, öğrencinin **neden yanlış düşündüğünü** tahmin etmektir.

**Canlı oyun:** https://yildirimgil.github.io/Kimya-Oyunu/

## Nasıl çalışır?

- Çoktan seçmeli soruların yanlış şıkları, kimya eğitiminde sık görülen **kavram yanılgılarına** bağlanmıştır.
- Her yanılgı için sabit "var/yok" yerine bir **olasılık** tutulur (başlangıç %20). Yanılgıya işaret eden şık seçilirse olasılık Bayesçi güncelleme ile artar (odds × 6), aynı konuda doğru cevap verilirse azalır (odds × 0.55). Olasılık %55'i geçince yanılgı "teşhis edildi" sayılır.
- **Kök neden ipucu:** Bir yanılgının hangi önceki konudaki eksikten kaynaklanabileceğini, yalnızca o konu çözülmüşse gösterir.
- **Bilişsel çatışma soruları:** Yanılgı ilk kez teşhis edildiğinde öğrenciyi kendi mantığının çelişkisiyle yüzleştiren takip sorusu sorulur.
- **Nüks takibi:** Daha önce çözülmüş görünen bir yanılgı geri gelirse işaretlenir.
- **Yeni yanılgı adayı keşfi:** Kütüphanede tanımlı olmayan ama birden çok öğrencinin seçtiği yanlış şıklar aday olarak listelenir.
- **Adaptif soru sıralaması:** Teşhisi en belirsiz yanılgıyı netleştirecek sorular öne alınır.
- **Öğretmen paneli:** Sınıf (9-A ... 12-B) ve okul numarasına göre konu yoğunluğu ve öğrenci listesi.

## Teknik yapı

Tek dosyalık saf HTML, CSS ve JavaScript uygulamasıdır (framework yok). Oturum verileri Firebase Firestore'a REST API ile kaydedilir. Çalışma tavsiyesi metinleri, tespit edilen yanılgılara göre **kural tabanlı yerel motor** tarafından üretilir; üretken yapay zekâ kullanılmaz.

## Gizlilik

Öğrenciden isteğe bağlı olarak yalnızca **sınıf/şube** ve **okul numarası** alınır. Ad-soyad toplanmaz. Veriler Firebase'de saklanır.

## Yapay zekâ kullanımı beyanı

Bu projenin kodlanmasında Claude (Anthropic) yapay zekâ asistanından yardım alınmıştır.

## Durum ve sınırlılıklar

- Proje pilot aşamasındadır; gerçek öğrenci denemeleri sürmektedir.
- Çoğu yanılgı şu an tek bir soruyla ölçülmektedir; bu, tek bir yanlışın (dikkat hatasının) yanılgı sanılma riskini artırır.
- Yanılgı listesi kimya eğitimi literatürüne dayanır; her yanılgı için kaynak doğrulaması yapılmaktadır.

## Telif ve kullanım

© 2026 [Ahmet YILDIRIM]. **Tüm hakları saklıdır.**

Bu depodaki kaynak kodu ve soru bankası yalnızca inceleme amacıyla görüntülenebilir. Yazarın yazılı izni olmadan kopyalanamaz, değiştirilip dağıtılamaz veya ticari amaçla kullanılamaz.

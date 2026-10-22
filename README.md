# Gezgin 🧭

**Senin gibi gezginlerin gözünden şehirler.**
Profiline göre kalacak yer, restoran ve gezilecek yer öneren; yorumları yazan kişinin yaşını, mesleğini ve gezme tarzını gösteren yapay zekâ destekli seyahat rehberi.

*[English below](#english)*

> ENGR 4451 Generative AI dersi kapsamında geliştirildi. Tripadvisor'dan ilham alındı. Tripadvisor 2025'te 1,89 milyar dolar gelir açıkladı.

## Canlı demo

👉 **https://emrehanvural.github.io/gezgin/**

Telefonda açıp ana ekrana ekleyebilirsin. Kurulum gerekmez.

## Neden farklı?

Tripadvisor'da 4,5 yıldızlı bir otel 21 yaşındaki bir öğrenci için de 60 yaşındaki bir emekli için de aynı görünür. Gezgin'de her yorumun yanında yazanın **yaş grubu, mesleği ve kiminle gezdiği** görünür. **"Benim gibiler"** filtresi de sana benzeyenlerin yorumlarını öne çıkarır.

## Özellikler

| Özellik | Açıklama |
|---|---|
| 👤 **Adım adım profil** | Yaş, meslek, kiminle gezdiğin, bütçe ve ilgi alanları sorulur. Profil kaydedilmez; sayfa her açıldığında yeniden sorulur. |
| 🏙️ **17 şehir** | Türkiye: İstanbul, İzmir, Ankara, Antalya, Bursa, Eskişehir, Trabzon, Gaziantep, Kapadokya. Yurt dışı: Paris, Roma, Londra, Barselona, Amsterdam, Berlin, Prag, Viyana. |
| 🎯 **Uyum puanı** | Her mekân profiline göre sıralanır ve nedenleri yazılır: "İlgine uygun: Tarih & kültür", "Bütçene uygun" gibi. |
| 👯 **Gezgin ikizin** | Sana en çok benzeyen gezginlerin o şehirdeki favorileri. |
| 🗺️ **Nereye?** | 18 hobi, mevsim, süre, bütçe ve tempo sorularıyla sana uygun şehirleri sıralar. |
| 🎁 **Beni şaşırt** | Kart dönerek sürpriz bir şehir açılır, altında 2 günlük plan gelir. |
| 📸 **Burası neresi?** | Bir yerin fotoğrafını yükle, yapay zekâ tanıyıp sayfasını açsın. |
| 🎧 **Sesli mini rehber** | Bir yerin kısa hikâyesini yazar, telefon sesli okur. |
| 🛂 **Gezi pasaportu** | Gittiğin yerlere damga bas, rozet kazan. |
| 🌅 **Canlı silüetler** | Her şehrin kendi silüeti, o şehrin gerçek saatine göre sabah, gündüz, gün batımı ve gece olarak çizilir. |
| 🌐 **Türkçe / İngilizce** | Tek dokunuşla dil değişir; yapay zekâ yanıtları da seçilen dilde gelir. |

## Yapay zekâ kurulumu (ücretsiz)

Gün planı, yorum özeti, fotoğraftan yer tanıma, sesli rehber ve sürpriz plan için bir **Google Gemini API anahtarı** gerekir:

1. [aistudio.google.com/apikey](https://aistudio.google.com/apikey) adresinden ücretsiz anahtar oluştur.
2. Gezgin'de **Profil** sekmesindeki **Yapay zekâ bağlantısı** alanına yapıştır ve **Kaydet**'e bas.

Anahtar yalnızca senin cihazında saklanır ve sadece Google'a gönderilir. **Anahtarını bu depoya ya da koda asla ekleme.**

## Bu sürümde veriler nerede?

- **Profil:** hiçbir yerde saklanmaz.
- **Yorumlar, damgalar, dil tercihi:** tarayıcının yerel depolamasında, yani sadece o cihazda.
- Yorumların herkes tarafından görülmesi için ortak bir veritabanı (ör. Supabase) bağlanabilir. Ders sürümü Claude üzerinde ortak veritabanıyla çalışır.

## Teknik yapı

- Tek dosya: `index.html` (HTML + CSS + JavaScript). Derleme ya da sunucu gerekmez.
- Şehir silüetleri resim değil; sayfa içinde `<canvas>` ile çizilir.
- Yapay zekâ: Claude içinde açıldığında Claude, diğer her yerde Google Gemini API.
- Sesli okuma tarayıcının kendi konuşma motorunu (Web Speech API) kullanır.

### Kendi bilgisayarında çalıştırma

```bash
git clone https://github.com/emrehanvural/gezgin.git
cd gezgin
python3 -m http.server 8000
# tarayıcıda http://localhost:8000 adresini aç
```

## Uyarı

Mekân bilgileri bilinen, köklü yerlerden derlenmiştir; fiyat ve çalışma saatleri değişmiş olabilir. Gitmeden haritadan kontrol et. Yapay zekâ yanıtları tahmindir.

---

## English

**Cities through the eyes of travellers like you.**
An AI-powered travel guide that ranks places to stay, eat and visit for your profile, and shows each reviewer's age group, job and travel style, with a "people like me" filter.

**Live demo:** https://emrehanvural.github.io/gezgin/

**Features:** step-by-step profile (not saved; asked again on every visit) · 17 cities in Turkey and Europe · match scores with reasons · travel twins · "Where should I go?" city finder · surprise trip · photo place recognition · audio mini guide · travel passport with stamps and badges · live skylines drawn for each city's local time · Turkish/English.

**AI setup (free):** create a Gemini API key at [aistudio.google.com/apikey](https://aistudio.google.com/apikey) and paste it into **Profile → AI connection**. The key stays in your browser and is sent only to Google. Never commit your key to this repository.

**Data in this version:** the profile is never stored; reviews, stamps and language stay in the browser on that device.

**Run locally:** clone the repo, run `python3 -m http.server 8000` in the folder and open `http://localhost:8000`.

# 🏠 UgoSmart OS — Sunucusuz Çok Platformlu Akıllı Ev Otomasyon Merkezi

![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20Android%20%7C%20Windows%20%7C%20ESP32-0ea5e9?style=flat-square)
![Architecture](https://img.shields.io/badge/Mimari-Sunucusuz%20Yerel%20A%C4%9F%20(LAN)-10b981?style=flat-square)
![AI](https://img.shields.io/badge/AI-Gemini%202.5%20Flash%20%2B%20Web%20Speech-8b5cf6?style=flat-square)
![License](https://img.shields.io/badge/Lisans-MIT-f59e0b?style=flat-square)

**UgoSmart OS**, Raspberry Pi veya harici bir merkezi sunucuya ihtiyaç duymadan; doğrudan ev içi yerel ağ (LAN) üzerindeki **ESP8266 / ESP32 / ESP32-S3** röle modülleri, **Akıllı TV**, **Windows PC** ve **Spotify Connect** hoparlörlerini tek bir modern arayüzden yöneten dağıtık akıllı ev sistemidir.

---

## ✨ Öne Çıkan Özellikler

* **Sunucusuz Yerel Ağ Mimarisi:** Tüm cihaz yapılandırmaları, oda tanımları ve sistem ayarları tarayıcının `localStorage` hafızasında tutulur; aylık abonelik veya bulut bağımlılığı yoktur.
* **Dağıtık ESP Röle & Dimmer Düğümleri:**
  * Duvar anahtarları (5A/10A) ve yüksek güçlü prizler (16A) için bağımsız HTTP uçları (`/status`, `/relay`, `/pwm`).
  * **İnternet/Wi-Fi Kesintisine Dayanıklı Donanım:** Duvar anahtarları ESP'nin kuru kontak (`SW_PIN`) girişine bağlandığı için ağ kopsa bile fiziksel anahtarlar gecikmesiz çalışmaya devam eder.
* **Canlı Enerji & İklim İzleme:**
  * Açık yüklere göre anlık **Akım (A)**, **Gerilim (V)**, **Aktif Güç (W)** ve **Toplam Tüketim (kWh)** göstergeleri ile tek tıkla **Ana Kesici**.
  * Odalar için sıcaklık/nem takibi ve Open-Meteo üzerinden canlı hava durumu tahmini.
* **Gemini AI & Türkçe Sesli Komut Motoru:**
  * **Web Speech API (`tr-TR`)** ve **TTS (Sesli Yanıt)** desteği.
  * *"Salon ışığını kapat, TV'den Kurtlar Vadisi aç, Spotify'da müzik çal ve PC'de teklif dosyasını bul"* gibi çok adımlı doğal cümleleri **Gemini 2.5 Flash** (veya yerleşik yerel ayrıştırıcı) ile ayrıştırıp eşzamanlı yürütür.
* **Akıllı TV & Windows PC Entegrasyonu:**
  * Android TV / Google TV üzerinde ADB üzerinden dizi, film, YouTube ve Netflix başlatma.
  * Windows bilgisayarda dosya arama ve uzaktan açma.
* **Dahili ESP `.ino` Stüdyosu & İndirme Merkezi:**
  * Tarayıcı içinden kart tipine (`ESP32-S3`, `ESP32`, `ESP8266`) ve sabit IP'ye göre canlı `.ino` kodu üretme, sanal kart simülasyonu ve **Web Serial API** ile USB üzerinden doğrudan test/izleme.
  * Kişiselleştirilmiş `.ino`, `pc_tv_bridge.py`, Android Studio kaynak kodları ve şifreli sistem yedeklerini tek tıkla indirme.

---

## 📁 Proje Klasör Yapısı

```text
UgoSmart-OS/
├── index.html                  # Ana Web & Android PWA Kontrol Paneli (Tek Dosya)
├── esp_node/
│   └── esp_node.ino            # ESP32 / ESP8266 Röle, PWM Dimmer ve Fiziksel Anahtar Kodu
├── pc_tv_bridge/
│   ├── pc_tv_bridge.py         # Windows PC Dosya Arama & Android TV ADB Köprü Servisi
│   └── baslat_pc_ajan.bat      # Windows Tek Tıkla Başlatma Betiği
├── android_native/
│   ├── MainActivity.java       # Android Studio Yerel Sesli Kontrol & HTTP İstemcisi
│   └── activity_main.xml       # Android Arayüz Tasarımı
└── README.md

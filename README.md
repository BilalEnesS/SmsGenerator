# Marka Analiz ve SMS Reklam Üretme Uygulaması

Bu proje, bir web sitesinden marka bilgilerini analiz edip özetleyen ve belirli bir kampanya bilgisine göre OpenAI'nin GPT-4 modelini kullanarak SMS reklamları oluşturan bir Flask tabanlı web uygulamasıdır.

## Özellikler
- Belirtilen bir web sitesinin başlık, meta açıklama, hakkımızda sayfası gibi bilgilerini çeker.
- OpenAI API kullanarak marka hakkında kısa bir özet oluşturur.
- Kampanya bilgilerine göre 3 farklı SMS reklam metni önerisi üretir.

## Gereksinimler
Bu projeyi çalıştırmak için aşağıdaki bağımlılıkların yüklü olması gerekmektedir:

- Python 3.x
- Flask
- requests
- BeautifulSoup4
- OpenAI

Gereksinimleri yüklemek için:
```bash
pip install flask requests beautifulsoup4 openai
```

## Kurulum ve Kullanım
1. **Projeyi klonlayın:**
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```
2. **API anahtarınızı ekleyin:**
   `app.py` dosyasındaki `openai.api_key` kısmına kendi OpenAI API anahtarınızı girin:
   ```python
   openai.api_key = "OPENAI-API-KEY"
   ```
3. **Uygulamayı çalıştırın:**
   ```bash
   python app.py
   ```
4. **Web arayüzüne erişin:**
   Tarayıcınızda `http://127.0.0.1:5000/` adresini açarak uygulamayı kullanabilirsiniz.

## API Kullanımı
### **Ana Sayfa (/)**
- **Yöntem:** `GET`, `POST`
- **İşlev:** Form üzerinden girilen URL'den marka bilgilerini çeker, analiz eder ve SMS önerileri oluşturur.
- **Parametreler:**
  - `url`: Marka web sitesi
  - `manual_brand_name`: Manuel giriş için marka adı
  - `manual_description`: Manuel giriş için marka açıklaması
  - `discount_rate`: Kampanya indirim oranı
  - `campaign_type`: Kampanya türü
  - `campaign_details`: Kampanya detayı
  - `sms_count`: Gönderilecek SMS sayısı (1 veya 2 SMS uzunluğu için)
  - `sector`: Marka sektörü
  - `message_tone`: SMS mesaj tonu
  - `start_date`, `end_date`: Kampanya tarih aralığı
  - `address`: Kampanya adres bilgisi

## Örnek Çalışma
1. **Bir web sitesi URL’si girildiğinde:**
   - Uygulama, marka bilgilerini çeker.
   - OpenAI ile kısa bir marka özeti oluşturur.
   - Kampanya detaylarına göre 3 farklı SMS önerisi üretir.

2. **Manuel giriş yapıldığında:**
   - Kullanıcı marka adı ve açıklamasını manuel girer.
   - Aynı süreçler uygulanarak SMS reklam önerileri oluşturulur.

## Önemli Notlar
- OpenAI API anahtarınızı güvenli tutun ve GitHub'a açık şekilde yüklemeyin.
- SMS karakter sınırları dikkate alınarak mesajlar üretilir.
- Web sitesinin hakkımızda sayfasını bulamazsa özet eksik olabilir.

## Lisans
Bu proje MIT Lisansı altında sunulmaktadır.


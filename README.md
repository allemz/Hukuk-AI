# Hukuk AI Asistanı

> **Yapay Zeka Dersi Dönem Projesi**

Bu projeyi, üniversitedeki **Yapay Zeka** dersimiz kapsamında 3 kişilik ekip olarak geliştirdik. Amacımız; Büyük Dil Modellerini (LLM) ve RAG (Retrieval-Augmented Generation) mimarisini kullanarak, hukuk gibi karmaşık bir alanda asistanlık yapabilecek, gerçek dünya problemlerine çözüm üreten bir uygulama ortaya koymaktı.

Proje, sadece hazır bir API'ye soru sormaktan ibaret değildir; vektör veritabanı yönetimi, canlı veri kazıma (scraping) ve doküman işleme gibi farklı modülleri tek bir çatı altında toplar.

** TAMAMLANMADI ** : Emsal kararlar sadece kararları ve tarihlerini veriyor, tam olarak davanın içeriğini çekmiyor ilerleyen zamanlarda eklenebilir.

---

## Projenin Amacı ve Çözdüğü Sorunlar

Hukukçuların ve öğrencilerin en büyük sorunu olan "doğru bilgiye hızlı erişim" ve "doküman analizi" süreçlerini otomatize etmeyi hedefledik.
* **Canlı Veri Entegrasyonu:** Statik verinin yetmediği yerde, **UYAP Emsal** sistemine bağlanıp anlık karar arayan ve bunları analiz eden bir yapı kurduk.

## Teknik Altyapı

Projeyi geliştirirken kullandığımız teknolojiler:

* **Frontend :** Python Streamlit
* **LLM :** Groq API (Llama-3-70b modelini hızı ve başarısı sebebiyle tercih ettik)
* **Backend:** `asyncio` ve `httpx` (UYAP Emsal'den asenkron veri çekmek için)
* **Veri İşleme:** `PyPDF2`, `python-docx`, `MarkItDown`

## Temel Özellikler

1.  **AI ile Hukuki Sohbet:** Kullanıcı sorusunu vektör veritabanındaki benzer kayıtlarla eşleştirip (Embedding) LLM'e bağlam olarak veriyoruz.
2.  **Canlı Emsal Arama:** UYAP Emsal API'sine istek atarak güncel Yargıtay/BAM kararlarını buluyor ve veritabanına ekleyebiliyoruz.
3.  **Döküman Analizi & Oluşturma:** Yüklenen sözleşmelerin risk analizini yapıyor veya sıfırdan dilekçe/sözleşme taslağı hazırlıyor.
4.  **Dava Yönetimi:** Dosya sistemi mantığıyla çalışan, not alınabilen bir vaka yönetim modülü.

## Kurulum ve Çalıştırma

Projeyi kendi bilgisayarınızda denemek için adımları takip edebilirsiniz:

1.  Repoyu klonlayın:
    ```bash
    git clone https://github.com/allemz/Hukuk-AI
    cd Hukuk-AI
    ```

2.  Gereksinimleri yükleyin:
    ```bash
    pip install -r requirements.txt
    ```

3.  Uygulamayı başlatın:
    ```bash
    streamlit run app.py
    ```

> **Not:** Uygulamanın çalışması için ücretsiz bir **Groq API Key** almanız ve arayüzdeki ilgili alana girmeniz gerekmektedir.

##  Neler Öğrendik?

Bu süreçte ekip olarak şunları deneyimledik:
* verilerin (PDF, Docx) işlenerek Vector'e dönüştürülmesi.
* Asenkron programlama ile dış servislerden veri çekme süreçleri.
* Prompt Engineering teknikleri ile modelin hukuki dilde konuşmasını sağlama.
* Streamlit kütüphanesi ile hızlı prototip ve arayüz geliştirme.

## Geliştirici Ekip

* **Ali Emre Ötün** - https://github.com/allemz/
* **Volkan Yılmaz** - https://github.com/Volkan776/ ( Projenin orjinal Reposu : https://github.com/Volkan776/AJAN-RAG-PROJESI )
* **Emre Tulgarlar**

---
*Bu proje akademik amaçlarla geliştirilmiş olup, üretilen hukuki metinler profesyonel hukuk danışmanlığı yerine geçmez.*

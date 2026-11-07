# LLM Destekli Akıllı Aday Değerlendirme, Çalışan Performansı Tahmini ve Tükenmişlik Risk Analizi

Veri Madenciliği dersi grup projesi.

**Ekip:** Sude Binnaz Yeşilbaş (K1) · İclal Keçeci (K2) · Melike Topçu (K3) · Merjen Yagmyrova (K4)

## Proje ne yapıyor?

1. **CV değerlendirme:** PDF CV'leri okur, SBERT dil modeliyle 4 iş ilanına benzerliklerini puanlar ve en uygun 10 adayı sıralar.
2. **Tükenmişlik riski:** Çalışan verisiyle regresyon ve karar ağacı kurarak tükenmişlik riskini tahmin eder.
3. **3/6/9/12. ay performansı:** İşe alım bilgilerinin ilk yıl performansını ne kadar açıklayabildiğini sentetik veriyle gösterir.

Sistem kimseyi otomatik elemez; yalnızca sıralar ve öneri sunar.

## Sonuçlar

| Konu | Sonuç |
| --- | --- |
| CV eşleştirme (SBERT, ilk 10'da doğru meslek) | HR %100 · Accountant %100 · Sales %90 · Data Analyst %20 |
| CV eşleştirme (beceri listesi) | HR %100 · Accountant %90 · Sales %50 · Data Analyst %10 |
| Tükenmişlik – Model B (işe alım öncesi) | R² 0,690 · MAE 0,087 (basit yöntem 0,157) |
| Karar ağacı (sınır 0,5) | Doğruluk 0,85 · Kesinlik 0,78 · Yakalama 0,87 · F1 0,83 |
| 3/6/9/12. ay (sentetik veri) | R² 0,68 → 0,42 → 0,23 → 0,17 |
| Test case'ler | 10 testten 8'i geçti, 1'i kaldı, 1'i yapılamadı |

## Klasörler

| Klasör / dosya | İçerik |
| --- | --- |
| `proje.ipynb` | Tüm kod (Google Colab), çıktılarıyla birlikte |
| `docs/Analiz Raporu.docx` | Analiz raporu |
| `docs/Gereksinim ve Test Dokümanı.docx` | Müşteri gereksinimleri, fonksiyonel/genel gereksinimler, use case, kabul kriterleri, test case'ler |
| `Data/ilanlar.csv` | Kullanılan 4 örnek iş ilanı |
| `kontrol_tablosu.xlsx` | CV'lerin elle kontrol sonuçları |
| `requirements.txt` | Gerekli Python kütüphaneleri |

## Veri setleri (depoya yüklenmedi)

Lisans ve boyut nedeniyle veri setleri depoda yoktur. Kodu çalıştırmak için indirip Drive'daki proje klasörüne koyun:

- CV'ler: [Resume Dataset (Kaggle)](https://www.kaggle.com/datasets/snehaanbhawal/resume-dataset) → `CV_Proje_Verileri/`
- Tükenmişlik: [Are Your Employees Burning Out? (Kaggle)](https://www.kaggle.com/datasets/blurredmachine/are-your-employees-burning-out) → `Burnout_Verileri/train.csv`

### Drive'daki klasör yapısı

```
veri madenciliği proje/
├── CV_Proje_Verileri/     ← Kaggle Resume Dataset (Resume/ ve data/ klasörleri)
├── Burnout_Verileri/      ← train.csv
├── ciktilar/              ← kod çalışınca kendiliğinden oluşur
├── ilanlar.csv
└── proje.ipynb
```

Hücre 1, Drive'da adı "veri madencili" ile başlayan klasörü otomatik bulur.

CV metinlerini içeren `ciktilar/cv_tablosu.csv` gizlilik nedeniyle depoya yüklenmez.

## Nasıl çalıştırılır?

1. `proje.ipynb` dosyasını Google Colab'da açın.
2. Veri setlerini ve `Data/ilanlar.csv` dosyasını Drive'daki proje klasörüne koyun.
3. Çalışma zamanı → Tümünü çalıştır.

Not: Proje kodunun ve örnek ilan metinlerinin hazırlanmasında yapay zekâ asistanı Claude'dan yararlanılmıştır (ayrıntı: Analiz Raporu, Bölüm 2.3).

# ai-hr-analytics-system
Yapay Zeka Destekli CV Değerlendirme, Çalışan Performansı Tahmini ve Tükenmişlik Riski Analizi Sistemi
📁 ai-hr-analytics-system
├── 📁 Data
│   └── 📄 ilanlar.csv

## Sonuçlar

| Konu | Sonuç |
| --- | --- |
| CV eşleştirme (SBERT, ilk 10'da doğru meslek) | HR %100 · Accountant %100 · Sales %90 · Data Analyst %20 |
| CV eşleştirme (beceri listesi) | HR %100 · Accountant %90 · Sales %50 · Data Analyst %10 |
| Tükenmişlik – Model B (işe alım öncesi) | R² 0,690 · MAE 0,087 (basit yöntem 0,157) |
| Karar ağacı (sınır 0,5) | Doğruluk 0,85 · Kesinlik 0,78 · Yakalama 0,87 · F1 0,83 |
| 3/6/9/12. ay (sentetik veri) | R² 0,68 → 0,42 → 0,23 → 0,17 |
| Test case'ler | 10 testten 8'i geçti, 1'i kaldı, 1'i yapılamadı |

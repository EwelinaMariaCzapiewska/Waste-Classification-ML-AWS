# ♻️ Klasyfikacja Odpadów - Projekt ML w chmurze AWS

Projekt zespołowy na przedmiot Uczenie Maszynowe. System rozpoznaje 6 kategorii odpadów przy użyciu Deep Learningu.

## 📊 Wyniki projektu
- **Dokładność (Accuracy):** 71%
- **Model:** MobileNetV2 (Transfer Learning)
- **Środowisko:** Amazon SageMaker (ml.t3.medium)
- **Dane:** Garbage Classification Dataset (Kaggle)

### Wykresy uczenia
![Accuracy](wykresy.png)

## 🏗️ Architektura
W projekcie wykorzystaliśmy technologię **Computer Vision**. Zastosowaliśmy architekturę MobileNetV2, która jest zoptymalizowana pod kątem wydajności (idealna do systemów wbudowanych i chmurowych). Dane były przechowywane w **Amazon S3**, a proces treningu odbył się w usłudze **Amazon SageMaker**.

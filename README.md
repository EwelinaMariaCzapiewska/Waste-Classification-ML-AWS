# ♻️ Klasyfikacja Odpadów - Projekt ML w chmurze AWS

Projekt zespołowy na przedmiot Uczenie Maszynowe. System rozpoznaje 6 kategorii odpadów przy użyciu Deep Learningu.

## 📊 Wyniki projektu
- **Dokładność (Accuracy):** 71%
- **Model:** MobileNetV2 (Transfer Learning)
- **Środowisko:** Amazon SageMaker (ml.t3.medium)
- **Dane:** Garbage Classification Dataset (Kaggle)

### Wykresy uczenia
![Accuracy](wykresy.png)

## 📈 Szczegółowa analiza wyników

Poniżej znajduje się interpretacja uzyskanych wykresów, która potwierdza poprawność procesu treningowego:

*   **Dokładność (Accuracy):** Wykres po lewej pokazuje, że dokładność modelu systematycznie rosła. Zaczęliśmy od poziomu ok. 46%, a zakończyliśmy na **71%**. Udowadnia to, że model skutecznie uczył się rozpoznawać cechy specyficzne dla każdej z 6 kategorii odpadów.
*   **Stabilność (Generalizacja):** Kluczowe jest to, że linia niebieska (treningowa) i pomarańczowa (walidacyjna) idą blisko siebie. Oznacza to, że model nie wyuczył się zdjęć na pamięć (**brak overfittingu**), ale nabył umiejętność generalizacji, czyli poprawnego rozpoznawania obiektów, których wcześniej nie widział.
*   **Optymalizacja błędu (Loss):** Wykres po prawej pokazuje drastyczny spadek funkcji straty. Na początku błąd wynosił 1.4, a na końcu spadł do poziomu ok. 0.8. Świadczy to o tym, że zastosowany **optymalizator Adam** bardzo sprawnie korygował wagi modelu w odpowiedzi na popełniane błędy.

## 🔍 Wnioski z testów live
Podczas testów rzeczywistych (Live Demo) model wykazał się ciekawą zdolnością analizy tekstur. Przykładem był błyszczący papierek po batoniku, który został sklasyfikowany jako **metal**. Jest to technicznie uzasadnione, ponieważ opakowanie to jest metalizowane i posiada właściwości odblaskowe identyczne jak folia aluminiowa zawarta w zbiorze treningowym.

## 🏗️ Architektura
W projekcie wykorzystaliśmy technologię **Computer Vision**. Zastosowaliśmy architekturę MobileNetV2, która jest zoptymalizowana pod kątem wydajności (idealna do systemów wbudowanych i chmurowych). Dane były przechowywane w **Amazon S3**, a proces treningu odbył się w usłudze **Amazon SageMaker**.

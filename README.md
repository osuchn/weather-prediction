# Przewidywanie opadów na następny dzień

Klasyfikacja, czy następnego dnia wystąpią opady, na podstawie danych pogodowych. Projekt porównuje **trzy modele** (Random Forest, SVM, drzewo decyzyjne) w połączeniu z **czterema strategiami radzenia sobie z brakami danych** (baseline, simple / iterative / KNN imputer), oceniając nie tylko skuteczność, ale i koszt obliczeniowy.

## Wynik
Najlepszy model: **Random Forest + Simple Imputer** — F1 = **0.623**, accuracy = **0.857**.

Kluczowy wniosek: zaawansowana imputacja (iterative, KNN) **nie poprawiła** wyników względem prostego uzupełniania, a znacząco zwiększała czas obliczeń. Prostsze podejście okazało się najlepszym kompromisem.

## Zakres projektu
- **EDA** — eksploracja i wizualizacja danych pogodowych.
- **Obsługa braków** — porównanie usuwania danych vs simple / iterative / KNN imputer.
- **Modelowanie** — Random Forest, SVM, drzewo decyzyjne.
- **Ewaluacja** — accuracy, precision, recall, F1 oraz czas trenowania.

## Wnioski
- Zaawansowana imputacja nie dała przewagi nad prostą.
- Random Forest to najlepszy kompromis skuteczności i czasu; SVM osiąga podobne wyniki znacznie wolniej.
- Niski recall (~0.5) wynika z niezbalansowania klas.

## Stack
Python, scikit-learn, pandas, matplotlib

## Dane
Publiczny zbiór pogodowy. Danych nie dołączam do repozytorium; pełny kod i wyniki w notatniku.

## Uruchomienie
Otwórz notatnik w Colab (przycisk „Open in Colab" na górze) i odpal komórki po kolei.

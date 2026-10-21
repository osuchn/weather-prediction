# Przewidywanie opadów na następny dzień

Klasyfikacja, czy następnego dnia wystąpią opady, na podstawie danych pogodowych. Projekt porównuje **trzy modele** (Random Forest, SVM, drzewo decyzyjne) w połączeniu z **czterema strategiami radzenia sobie z brakami danych** (baseline, simple / iterative / KNN imputer), oceniając nie tylko skuteczność, ale i koszt obliczeniowy.

## Wynik
| Model | Strategia braków | Accuracy | Precision | Recall | F1 | Czas [s] |
|---|---|---|---|---|---|---|
| **Random Forest** | **Simple Imputer** | **0.857** | 0.750 | 0.533 | **0.623** | 20.6 |
| Random Forest | Baseline (usunięte rekordy) | 0.854 | 0.742 | 0.526 | 0.616 | 2.3 |
| SVM | Simple Imputer | 0.854 | 0.752 | 0.510 | 0.608 | 394.8 |
| Random Forest | Iterative Imputer | 0.856 | 0.772 | 0.497 | 0.605 | 30.6 |
| SVM | Baseline | 0.854 | 0.757 | 0.501 | 0.603 | 3.8 |
| Random Forest | KNN Imputer | 0.855 | 0.766 | 0.496 | 0.602 | 23.3 |
| SVM | KNN Imputer | 0.852 | 0.793 | 0.451 | 0.575 | 370.0 |
| SVM | Iterative Imputer | 0.851 | 0.792 | 0.448 | 0.572 | 367.8 |
| Drzewo decyzyjne | Baseline | 0.791 | 0.528 | 0.561 | 0.544 | 0.1 |
| Drzewo decyzyjne | Iterative Imputer | 0.788 | 0.521 | 0.531 | 0.526 | 1.9 |
| Drzewo decyzyjne | Simple Imputer | 0.780 | 0.502 | 0.548 | 0.524 | 1.5 |
| Drzewo decyzyjne | KNN Imputer | 0.780 | 0.503 | 0.532 | 0.517 | 1.3 |

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
Publiczny zbiór pogodowy, zbiór udostępniony przez prowadzącego zajęcia. Danych nie dołączam do repozytorium; pełny kod i wyniki w notatniku.

## Uruchomienie
Otwórz notatnik w Colab (przycisk „Open in Colab" na górze) i odpal komórki po kolei.

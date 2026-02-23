# Time-Series-Analysis
Statystyczna analiza i prognozowanie szeregów czasowych przygotowane w parze.

## Projekt 1: Dekompozycja i Analiza Stacjonarności

Pierwszy projekt skupia się na rygorystycznej ocenie stacjonarności sygnałów oraz porównaniu metod separacji składowych trendu i sezonowości.

**[Pobierz pełne Sprawozdanie w PDF](./time-series-decomposition-testing/raport1.pdf)**


#### Zadanie 1: Testowanie białoszumowości (Autor: [Michał](https://github.com/Bagietka-Michael))
* **Statystyczna weryfikacja szumu białego:** Implementacja formalnych testów statystycznych: **Boxa-Pierce’a** oraz **Ljungi-Boxa**.
* **Analiza porównawcza:** Zestawienie metod formalnych z podejściem graficznym.
* **Badania symulacyjne:** Przeprowadzenie symulacji **Monte Carlo** badających moc testów oraz błąd I rodzaju dla różnych rozkładów, długości szeregów i opóźnień.

#### Zadanie 2: Dekompozycja i eliminacja trendu (Autor: Mateusz Cieślak)
* **Eksploracyjna analiza szeregów (EDA):** Wykorzystanie wykresów sezonowych i podszeregów (**subseries plots**) do identyfikacji wzorców cyklicznych w danych o bezrobociu.
* **Metody dekompozycji (Benchmarking):**
    * **Ruchoma średnia (decompose):** Porównanie wariantów addytywnych i multiplikatywnych.
    * **Model regresji (tslm):** Modelowanie trendu wielomianami różnych stopni.
    * **Metoda STL (Loess):** Optymalizacja parametrów wygładzania.
* **Transformacja Boxa-Coxa:** Stabilizacja wariancji przy użyciu parametru $\lambda$ wyznaczonego **metodą Guerrero**. Ocena jakości dopasowania za pomocą miary **RMSE**.
* **Analiza stacjonarności reszt:** Porównanie skuteczności eliminacji trendu poprzez dekompozycję vs. różnicowanie danych w celu uzyskania szumu białego.

#### Narzędzia matematyczne:
Autokorelacja (ACF/PACF), testy Ljung-Box, dekompozycja STL, transformacja Boxa-Coxa, błąd średniokwadratowy (RMSE), symulacje stochastyczne.

#### Wykorzystane biblioteki R:
`forecast`, `tseries`, `ggplot2`, `TSAFBook`, `fpp2`.

## Projekt 2: Modelowanie autoregresyjne i prognozowanie (TSLM, SARIMA, ETS)

Druga część poświęcona jest zaawansowanym technikom modelowania stacjonarnych i niestacjonarnych szeregów czasowych oraz weryfikacji trafności prognoz ex-post.

**[Pobierz pełne Sprawozdanie w PDF](./time-series-modeling-and-forecasting/raport2.pdf)**

#### Zadanie 1: Modelowanie Autoregresyjne danych klimatycznych (Autor: [Michał](https://github.com/Bagietka-Michael))
* **Stacjonaryzacja danych:** Analiza szeregu `gtemp_both` (anomalie temperatury) poprzez różnicowanie oraz eliminację trendu wielomianowego.
* **Identyfikacja modelu AR(p):** Dobór rzędu modelu przy użyciu funkcji **PACF** oraz kryteriów informacyjnych **AIC** i **FPE**.
* **Estymacja i Walidacja:** Porównanie metod estymacji **Yule’a-Walkera** oraz **MLE**. Konstrukcja asymptotycznych przedziałów ufności dla parametrów oraz diagnostyka reszt pod kątem białoszumowości.

#### Zadanie 2: Prognozowanie wskaźników ekonomicznych (Autor: Mateusz Cieślak)
* **Budowa modeli prognostycznych:** Implementacja i optymalizacja modeli klasy **SARIMA**, **ETS** oraz **TSLM** dla danych `euretail`.
* **Proces modelowania:** Samodzielna identyfikacja struktury sezonowej, wyznaczanie rzędów różnicowania oraz analiza istotności dryfu.
* **Ewaluacja prognoz ex-post:**
    * Porównanie modeli z naiwnymi metodami referencyjnymi (**SNaive**).
    * Ocena dokładności na zbiorze testowym za pomocą miar: **RMSE**, **MAE**, **MAPE** oraz **MASE**.
    * Wizualizacja i interpretacja prognoz w kontekście zmian strukturalnych trendu.

#### Narzędzia matematyczne:
Modele AR(p), SARIMA, ETS, kryteria AIC/FPE, równania Yule’a-Walkera, estymacja MLE, weryfikacja prognoz ex-post.

#### Wykorzystane biblioteki R:
`forecast`, `astsa`, `fpp2`, `tseries`, `ggplot2`, `dplyr`.

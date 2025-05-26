# Prediktívna analýza dát v oblasti spotreby elektrickej energie
## Patrik Grivalský

```
ŠKOLITEĽ: doc. Ing. Martin Sarnovský, PhD.
ROK: 2024/2025
UNIVERZITA: Technická univerzita v Košiciach
FAKULTA: Fakulta Elektrotechniky a Informatiky
ŠTUDIJNÝ ODBOR: Informatika
ŠTUDIJNÝ PROGRAM: Hospodárska informatika
```

### Abstrakt
Bakalárska práca sa zameriava na prediktívnu analýzu spotreby elektrickej energie prostredníctvom modelovania priebehu činného výkonu v čase. Cieľom práce je porovnať presnosť troch rôznych algoritmov, Autoregressive Integrated Moving Average ako štatistického modelu, Extreme Gradient Boosting ako zástupcu algoritmov strojového učenia a Long-Short Term Memory ako model hlbokého učenia, ako aj odlišných prístupov k modelovaniu a trénovaniu. Teoretická časť sa venuje základom spotreby elektrickej energie, faktorom, ktoré ju ovplyvňujú, a významu jej predikcie. Sú predstavene vybrané štúdie z oblasti energetickej analýzy a opisujú sa metodiky spracovania dát, ako sú Proces objavovania znalosti v databázach a CRISP-DM. Súčasťou je aj prehľad algoritmov, časových radov a metrík na vyhodnotenie. Praktická časť práce zahŕňa analýzu dát, trénovanie predikčných modelov a ich následné vyhodnotenie.

### Obsah repozitára

- `pochopenie_dat.ipynb` – pochopenie a príprava dát  
- `LSTM_modelovanie.ipynb` – modelovanie pomocou LSTM  
- `SARIMA_modelovanie.ipynb` – modelovanie pomocou SARIMA  
- `XGBoost_modelovanie.ipynb` – modelovanie pomocou XGBoost
-  README.md --> aktuálny súbor s informáciami

### Požiadavky

1. Verzia Pythonu: 3.12.7 (testovaná verzia) alebo iná kompatibilná,  
   stiahnuteľná z: https://www.python.org/downloads/
2. JupyterLab  
3. Nainštalované knižnice

### Použité knižnice
- matplotlib => 3.9.2 (vizualizácie)
- pandas => 2.2.2 (manipulácia a predspracovanie dát)
- seaborn => 0.13.2 (korelačná matica)
- numpy => 1.26.4 (numerické výpočty)
- statsmodels => 0.14.2 (autokorelačná funkcia (PACF) a dekompozícia časového radu)
- scikit-learn => 1.5.1 (MinMaxScaler a metriky vyhodnotenia)
- xgboost => 3.0.0 (modelovanie pomocou XGBoost)
- tensorflow => 2.19.0 (modelovanie pomocou LSTM)
- pmdarima => 2.0.4 (modelovanie pomocou SARIMA)

##  Popis atribútov 

- *timestamp* – čas záznamu merania vo forme Unixového času (v sekundách)
- *U_L1* – napätie na fáze 1
- *U_L2* – napätie na fáze 2
- *U_L3* – napätie na fáze 3
- *U_cumulative* – súčet napätí cez všetky fázy
- *I_L1* – prúdový výkon na fáze 1
- *I_L2* – prúdový výkon na fáze 2
- *I_L3* – prúdový výkon na fáze 3
- *I_cumulative* – súčet prúdového výkonu cez všetky fázy
- *P_L1* – činný výkon na fáze 1
- *P_L2* – činný výkon na fáze 2
- *P_L3* – činný výkon na fáze 3
- *P_cumulative* – súčet činného výkonu cez všetky fázy (cieľová premenná)
- *Q_L1* – jalový výkon na fáze 1
- *Q_L2* – jalový výkon na fáze 2
- *Q_L3* – jalový výkon na fáze 3
- *Q_cumulative* – súčet jalových výkonov cez všetky fázy
- *hour* – hodina v rámci dňa (0–23) **novovytvorený atribút**
- *lag_1* – hodnota P_cumulative posunutá o 1 hodinu dozadu (lag) **novovytvorený atribút**
- *lag_24* – hodnota P_cumulative posunutá o 24 hodín dozadu (lag) **novovytovreny atribut**

  

# Cyfrowe przetwarzanie sygnałów i obrazów – Laboratorium  
**Przetwarzanie i analiza sygnału EKG**  
**Prowadzący:** Jacek Cichosz  
**Katedra Systemów i Sieci Komputerowych, Politechnika Wrocławska, Wrocław**

---

## Plan ćwiczeń laboratoryjnych

1. **Platforma testowa**
2. **Testowe sygnały EKG**
3. **Analiza okresowych sygnałów w dziedzinie częstotliwości**
4. **Analiza sygnału EKG w dziedzinie częstotliwości**
5. **Filtracja sygnału EKG**

---

## Platforma testowa

### Ćwiczenie 1 – Wczytywanie i wizualizacja sygnałów
Zadaniem jest napisanie skryptu w Pythonie lub Matlabie umożliwiającego:
- Wczytywanie sygnałów EKG w formacie tekstowym.
- Wizualizację wycinka sygnału dla zadanego przedziału czasowego.
- Skalowanie osi wykresów i ich opis.
- Zapis dowolnego wycinka sygnału do pliku o podanej nazwie.

**Uwagi dotyczące plików EKG:**
- Wiersze plików odpowiadają kolejnym próbkom sygnału.
- Kolumny odpowiadają różnym odprowadzeniom EKG.
- Niektóre pliki zawierają czas w pierwszej kolumnie, a wartości sygnału w drugiej.
- Pliki testowe:
  - `ekg1.txt` – 12 kolumn (odprowadzenia), `fs = 1000 Hz`
  - `ekg100.txt` – 1 kolumna, `fs = 360 Hz`
  - `ekg_noise.txt` – 1 kolumna: czas, 2 kolumna: amplituda, `fs = 360 Hz`

---

## Częstotliwościowa analiza sygnałów

### Ćwiczenie 2 – Analiza sygnałów okresowych
Celem jest praktyczne użycie funkcji `numpy.fft` i `numpy.ifft`:
1. Wygenerować ciąg próbek odpowiadający fali sinusoidalnej o częstotliwości 50 Hz i długości 65536.
2. Wyznaczyć dyskretną transformatę Fouriera i przedstawić widmo amplitudowe w zakresie `[0, fs/2]`.
3. Wygenerować mieszaninę dwóch fal sinusoidalnych (50 Hz i 60 Hz) i przedstawić widmo.
4. Powtórzyć eksperymenty dla różnych czasów trwania sygnałów i częstotliwości próbkowania.
5. Wyznaczyć odwrotne transformaty Fouriera i porównać z sygnałami oryginalnymi.

### Ćwiczenie 3 – Analiza sygnału EKG w dziedzinie częstotliwości
1. Wczytać sygnał `ecg100.txt` i ocenić go wizualnie.
2. Wyznaczyć dyskretną transformatę Fouriera i przedstawić widmo amplitudowe w funkcji częstotliwości `[0, fs/2]`.
3. Wyznaczyć odwrotną dyskretną transformatę Fouriera i porównać z sygnałem pierwotnym.

---

## Filtracja sygnału EKG

### Ćwiczenie 4 – Redukcja zakłóceń
1. Wczytać sygnał `ekg_noise.txt` i ocenić zakłócenia.
2. Zastosować filtr dolnoprzepustowy (np. Butterwortha) o częstotliwości granicznej 60 Hz:
   - Wyznaczyć parametry filtra.
   - Wykreślić charakterystykę tłumienia.
   - Przedstawić przebieg sygnału po filtracji i jego widmo.
3. Zastosować filtr górnoprzepustowy o częstotliwości granicznej 5 Hz w celu eliminacji pływania linii izoelektrycznej.
4. Połączenie filtrów dolno- i górnoprzepustowego tworzy filtr pasmowoprzepustowy `[5, 60] Hz`.

---

## Literatura

1. Dyskretna transformacja Fouriera: [numpy.fft](https://docs.scipy.org/doc/numpy/reference/routines.fft.html), 2020  
2. W. Myszka. Jupyter: [Instrukcja Jupyter](https://kmim.wm.pwr.edu.pl/myszka/dydaktyka/metodynumeryczne/dodatki/jupyter/), 2020  
3. W. Myszka. Szybka transformata Fouriera: [FFT Notebook](https://nbviewer.jupyter.org/urls/temisto.immt.pwr.wroc.pl/~myszka/Jupyter/FFT.ipynb), 2020  
4. Numpy Tutorial: [cs231n.github.io](http://cs231n.github.io/python-numpy-tutorial/), 2020  
5. Samouczek Pythona: [learnpython.org](https://www.learnpython.org/pl/), 2020  
6. Scipy Lecture Notes: [scipy-lectures.org](https://scipy-lectures.org/), 2020  
7. scipy.signal: [docs.scipy.org](https://docs.scipy.org/doc/scipy/reference/signal.html), 2020  
8. The Python Tutorial: [docs.python.org](https://docs.python.org/3/tutorial/), 2020
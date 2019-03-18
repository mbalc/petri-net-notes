# Wykład 3
> Miejsce $$p$$ jest *ograniczone* w sieci $$N=\langle P,T,F \rangle$$ przy początkowym markowaniu $$M_0 \leftrightarrow \exists k \in \mathbb{N} : \forall_{M \in[M_0]}:M[p] \leq k$$

## Zadanie

Czy istnieje sieć $$N$$ i markowanie początkowe $$M_{0}$$ takie, że
i) $$M_{0}$$ jest żywe
ii) istnieją dwa miejsca $$p_1, p_2 \in P$$ t.że $$p_1$$ oraz $$p_2$$ nie są ograniczone przy $$M_{0}$$
iii) istnieje taka stała $$k$$, że $$\forall_{M \in [M_0]} M(p_1) < k \vee M(p_2) < k$$ ? (istnieje! pokaż to)


## Ograniczoność

> **Fakt:** Markowanie $$M_{0}$$ jest ograniczone $$\leftrightarrow $$ każde miejsce jest ograniczone $$ \leftrightarrow$$ zbiór markowań osiągalnych jest skończony

> Problem ograniczoności: czy $$M_{0}$$ jest ograniczone w $$\mathcal{N}$$

---
###Twierdzenie (Karp/Miller 1968)
> Problem ograniczoności jest rozstrzygalny

#### Dowód
##### Konstrukcja drzewa pokrycia
Niech $$n=|P|$$. Węzłami drzewa będą wektory $$\mathbb{N}_{\omega}^n$$. Korzeniami będzie $$ M_{0}$$
Jeżeli $$M_1$$ jest węzłem drzewa i jeśli $$t$$ jest  aktywne przy $$M_1$$ oraz $$M_2 = M_1 + \vec{t}$$
Jezeli $$M_2$$ jeszcze nie wystąpił w drzewie, to na wszystkich wsþółrzędnych $$i$$ dla których na ścieżce od $$M_0$$ do $$M_2$$ istnieje markowanie $$M'$$ t.że $$M' \leq M_2$$ i $$M'[i]  < M_2[i]$$ kładziemy $$M_2[i] := \omega$$

Pokażemy, że drzewo pokrycia jest skończone. Załóżmy przeciwnie, że jest nieskończone. Spełnia założenia lematu Königa, więc istnieje w nim nieskończona ścieżka. Nieskończony ciag wektorów z tej ścieżki na mocy lematu Dicksona zawiera nieskończony podciąg niemalejący. Żadne dwa elementy tego ciągu nie mogą być równe, więc jest to ciąg rosnący. Ale w każdym kolejnym wyrazie tego ciągu liczba $$\omega$$ (omeg) rośnie, Może być ich jednak tylko co najwyżej $$n$$, bo taki jest rozmiar wektora. 

Markowanie $$M_0$$ jest ograniczone $$\leftrightarrow$$ w drzewie pokrycia nie ma omeg.

### Lemat Königa:
Jeśli każdy węzeł w drzewie ma skończony rząd a drzewo jest nieskończone, to istnieje w nim nieskończona ścieżka

### Lemat Dicksona
#### Wersja pierwsza
W każdym nieskończonym ciągu liczb naturalnych istnieje podciąg niemalejący
#### Uogólniony lemat Dicksona
Dotyczy zbioru $$\mathbb{N}_{\omega} = \mathcal{N} \cup \{\omega \}$$
$$\forall_{n \in \mathcal{N}} n < \omega$$
$$\omega \pm n = \omega$$

$$\forall_{n \in \mathcal{N}} n < \omega$$ Każdy nieskończony ciag wektorów $$\mathbb{N}_{\omega}^n$$ zawiera nieskończony ciąg niemalejący.

##### Dowód
indukcja; Dla $$n=1$$ - prawie Lemat Dicksona. . Dla nieskończonej liczby $$\omega$$ - podciąg stały; a dla skończonej - lemat Dicksona od ostatniego wystąpienia $$\omega$$


###### Krok indukcyjny
Zakładamy, że dla $$k < n$$ teza zachodzi
Skupmy się na pierwszych $$n - 1$$ współrzędnych. Na mocy założenia indukcyjnego wektory zrzutowane na te współrzędne mają nieskończony podciąg niemalejący. Z niego wybieramy $$k$$ elementy, które na ostatnije wsþółrzędnej tworzą nieskończony podciąg niemalejący.

### Twierdzenie
Każda sieć dobrze zbudowane ma dodatni ($$>\vec{0}$$) T-niezmiennik, czyli $$\exists_{\vec{x} > \vec{0}}$$ t.ze $$CX = 0$$

#### Dowód
Dobrze zbudowana $$\rightarrow \exists$$ markowanie $$M_0$$, które jest żywe i ograniczone. 
$$M_0 \xrightarrow{\sigma_{01}} [t_1 \rangle M_{01} \xrightarrow{\sigma_{02}} [t_2 \rangle M_{02} \dots \xrightarrow{\sigma_{0n}} [t_{0n} \rangle M_{0n}$$
$$C \cdot \#(\sigma_{01}t_1\sigma_{02}t_2\dots\sigma_{0n}t_n)= 0$$ jeśli $$M_0 = M_{0n}$$

# Ćwiczenia
## zadanie 1
Szukamy sieci z markowaniem $$M_0$$ dla którego graf pokrycia jest silnie spójny i zawiera wszystkie zdarzenia na krawędziach, ale $$M_0$$ nie jest żywe.
> Odp.: nie ma, bo każdy graf z $$\omega$$ nie będzie silnie spójny, a każdy skończony graf będzie miał żywe markowanie

## zadanie 2
Szukamy sieci z markowaniem $$M_0$$ dla którego graf pokrycia ma wszystkie finały będące silnie spójnymi składowymi i zawierające wszystkie zdarzenia na krawędziach, ale $$M_0$$ nie jest żywe.

Udowodnij że dobrze zbudowana -> graf sieci jest silnie spojny (ignorujac pionki, samymi strzalkami)
# Wykład 2

## Vector Addition Systems (System dodawania wektorów)

 $$\{ v_1,\dots,v_k \in \mathbb{Z}^n , m \in \mathbb{N}^n\}$$, $$m$$ - stan początkowy
$$[m]$$ - zbiór stanów osiągalnych - najmniejszy podzbiór $$\mathbb{N}^n$$ że:
- $$m \in [m]$$
- jeśli $$m' \in [m]$$ i $$\exists_{i=1,\dots,k} : m' + v_k \in \mathbb{N}^n$$, to $$m' + v_i \in [m]$$


Rys 1 ![](http://i.markdownnotes.com/image_09eC4RZ.jpg)

Schemat macierzy incydencji sieci $$<P,T,F>$$ ![](http://i.markdownnotes.com/image_8cRpXh7.jpg)

### Problem osiągalności
dla danego systemu dodawania wektorów $${v_1,\dots,v_k,m}$$ oraz stanu $$m' \in \mathbb{N}^n$$ rozstrzygnąć, czy $$m' \in [m]$$

Niech $$<V, E>$$ będzie grafem osiągalności dla markowania początkowego $$m$$ w sieci $$\mathcal{N}=<P,T,F>$$

Definiujemy relację $$\varrho \subseteq V \times V$$:
$$v_1 \varrho v_2 \leftrightarrow \exists_{\text{ścieżka z} v_1 \text{do} v_2} \wedge \exists_{\text{ścieżka z} v_2 \text{do} v_1} $$

**Fakt:** $$\varrho$$ jest relacją równoważności
Zbiór klas abstrakcji tej relacji tworzy DAG (skierowany graf bez cykli)
Powiemy że dwie klasy abstrakcji $$[m_1]$$ i $$[m_2]$$ są połączone krawędzią w tym grafie $$\leftrightarrow$$ z $$m_1$$ istnieje ścieżka do $$m_2$$ w grafie osiągalności

####Własności markowań w sieciach Petriego
1. Markowanie jest odtwarzalne $$\leftrightarrow |[m]| > 1 \wedge$$ zbiór węzłów grafu zredukowanego jest jednoelementowy (cały graf jest jedną spójną składową); eng. *home state*
2. Markowanie jest martwe $$\leftrightarrow$$ żadne ze zdarzeń nie jest aktywne (prawie $$|[m]| = 1$$, ale np. sieć - jeden katalizator - ma nie spełniać)
3. Markowanie jest nieblokujące się $$\leftrightarrow \forall_{m' \in [m]}$$ $$m'$$ nie jest martwe
4. Markowanie jest żywe $$\leftrightarrow \forall_{m' \in [m]} \forall_{t \in T} \exists_{m''\in [m']} m''[t\rangle$$ 
5. Markowanie jest ograniczone $$\leftrightarrow |[m]| < \infty$$
  a. Elementarna sieć jest bezpieczna (1-ograniczona) (eng.: *safe*, *1-bounded*) $$\leftrightarrow \forall_{m'\in[m]} \forall_{p \in \bullet t} m'(p) = 1 \rightarrow \forall_{q \in t\bullet \setminus \bullet t} m'[q]=0$$
  
  Powiemy, że sieć jest *dobrze zbudowana* $$\leftrightarrow$$ istnieje markowanie $$m$$ w tej sieci, które jest jednocześnie żywe i ograniczone
  
  Sieć jest strukturalnie żywa $$\leftrightarrow$$ istnieje dla niej żywe markowanie
  Sieć jest strukturalnie ograniczona $$\leftrightarrow$$ każde markowanie jest ograniczone
  

  > **Ciekawostka:** niedawno udowodniono, że problem osiągalności jest równoważny problemowi żywotności

##### Przykłady:
- Sieć nie martwa, ale nie żywa ![](http://i.markdownnotes.com/image_Jd0b5kp.jpg)
- Inny przykład ![](http://i.markdownnotes.com/image_eGZQzmC.jpg)
- sieć producent-konsument
  - nie jest dobrze zbudowana

### Macierz incydencji
> *Def.:* Macierz incydencji sieci $$\mathcal{N}=<P,T,F>$$ ma $$|P|$$ wierszy i $$|T|$$ kolumn
> $$c_{i,j} = -F(p_i, t_j) + F(t_j p_i)$$

#### Przykład
- Sieć producent-konsument ![](http://i.markdownnotes.com/image_YQEJc6l.jpg)
- Macierz incydencji tej sieci: ![](http://i.markdownnotes.com/image_Kn8kxK1.jpg)

#### Równanie stanu
Technika algebraiczna udowadniania, że pewne markowanie jest nieosiągalne

Gdy, $$M[t_{i_1},t_{i_2},\dots,t_{i_k}] > M'$$ to implikuje to $$M + C * \varepsilon_{i_1} + C * \varepsilon_{i_2} + \dots + C * \varepsilon_{i_k} = M + C * (\sum_{y \in \vec{i}}\varepsilon_{y}) = M'$$, $$C\vec{x} = M' - M$$ musi więc mieć rozwiązanie w $$\mathbb{N}^{|T|}$$

#### Twierdzenie Lautenbacha
- Jeśli $$y^T C = 0$$ i $$ M' \in [M]$$ to $$y^T M' = y^TM$$
##### Dowód
Jeśli $$M' \subset [M]$$ to układ równań 
$$\begin{cases}
M+C\vec{x} = M'\\
y^TM + y^TCx = y^TM'
\end{cases}$$ ma rozwiązanie
#### Teoria niezmienników
- rozwiązania $$C\vec{x} = 0$$ to T-niezmienniki (eng.: *t-invariant*)
- rozwiązania $$\vec{y}^TC = 0$$ to P-niezmienniki (eng.: *p-invariant*)
> *Fakt:* Jeśli istnieje dodatni P-niezmiennik sieci, to sieć jest strukturalnie ograniczona

> *Def.:* Sieć $$<P,T,F>$$ jest $$P$$-grafem $$\leftrightarrow$$ 
> $$\forall_{p\in P}: |\bullet p| <= 1 $$ oraz $$|p\bullet|<=1$$
> siecią z wolnym wyborem (eng.: *free-choice (FC)*) $$\leftrightarrow \forall_{p\in P} : |p\bullet| > 1 \rightarrow \forall_{t\in p\bullet} \{p\}=\bullet t$$ oraz dla $$t_1, t_2 \in p\bullet $$ zachodzi $$ F(p,t_1) = F(p,t_2)$$

## Zadania
- zrobic siec, gdzie markowanie jest nieodtwarzalne, ale zywe
- zrobic siec gdzie graf zredukowany stanowi romb A->B, B->D, A->C, C->D, gdzie D ma być żywe
- siec ktora jest zywa, ma dwa miejsca ktore sa nieograniczone, ale nie jednoczesnie
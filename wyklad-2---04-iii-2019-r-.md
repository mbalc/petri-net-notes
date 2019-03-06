# Wykład 2

## Vector Addition Systems (System dodawania wektorów

$$\{ v_1,\dots,v_k \in \mathbb{Z}^n , m \in \mathbb{N}^n\}$$, $$m$$ - stan początkowy
$$[m]$$ - zbiór stanów osiągalnych - najmniejszy podzbiór $$\mathbb{N}^n$$ że:
- $$m \in [m]$$
- jeśli $$m' \in [m]$$ i $$\exists_{i=1,\dots,k} : m' + v_k \in \mathbb{N}^n$$, to $$m' + v_i \in [m]$$


Rys 1 ![](https://cdn.mos.cms.futurecdn.net/NSQWRfjjNUgDNTvSeuRMRF-650-80.jpg)

Macierz incydencji sieci $$<P,T,F>$$ ![](https://cdn.mos.cms.futurecdn.net/NSQWRfjjNUgDNTvSeuRMRF-650-80.jpg)

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
  a. Elementarna sieć jest bezpieczna (1-ograniczona) (eng.: *safe*, *one-bounded*) $$\leftrightarrow \forall_{m'\in[m]} \forall_{p \in \bullet t} m'(p) = 1 \rightarrow \forall_{q \in t\bullet \setminus \bullet t} m'[q]=0$$
  
  Powiemy, że sieć jest *dobrze zbudowana* $$\leftrightarrow$$ istnieje markowanie $$m$$ w tej sieci, które jest jednocześnie żywe i ograniczone

##### Przykłady:


## Zadania
- zrobic siec, gdzie markowanie jest nieodtwarzalne, ale zywe
- zrobic siec gdzie graf zredukowany stanowi romb A->B, B->D, A->C, C->D, gdzie D ma być żywe
- siec ktora jest zywa, ma dwa miejsca ktore sa nieograniczone, ale nie jednoczesnie; dla kazdego k mozna zna
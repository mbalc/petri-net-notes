# Wykład 1

####Role pionków (dodatkowe): 
- Agent powalajacy zachodzic "reakcjom" 
- Dokument – idzie za biegiem reakcji 

###Definicje
#####Def.:
> Elementarna sieć Petriego to trójka uporządkowana $$<P, T, F>$$, gdzie $$P, T$$ - skończone i niepuste zbiory odpowiednio miejsc $$(\circ)$$ i zdarzen $$(\square)$$, zaś F $$(\rightarrow)$$ to funkcja $$F: (P \times T) \cup (T \times P) \rightarrow {0, 1}$$ 

#####Def.:

> Stan sieci (konfiguracja) to funkcja $M. P \rightarrow {0, 1}$ (przypisanie pinków miejscom) 

#####Ozn.  

$$\forall_{x \in P \sum T} \bullet x = \{y \in T \cup P   :    F(y, x) = 1\}$$ 

$$\forall_{x \in P \sum T} x \bullet = \{y \in T \cup P   :    F(x, y) = 1\}$$ 

 

#####Def.: 
>Zdarzenie $$t \in T$$ jest aktywne w stanie $$M$$ wtw $$\forall_{p \in \bullet x} M(p) = 1 \wedge \forall_{p \in x \bullet \setminus \bullet x} M(p) = 0$$ 

Zajście aktywnego zdarzenia t to funkcja $$[\bullet\rangle: M \times T \rightarrow M'$$ spełniająca warunki:  

- (1) $$t$$ jest aktywne w $$M$$ 

- (2) $$M'(p) = 
\begin{cases}
	0 \text{ jeśli } p \in \bullet t \setminus t \bullet\\
	1 \text{ jeśli } p \in t \bullet \setminus \bullet t\\
	M(p) \text{ wpr}
\end{cases}$$ 

#####Oznaczmy
- sym.: $$M [t\rangle M'$$ - $$M'$$ powstaje z $$M$$ w wyniku zajścia $$M$$ 

- sym.: $$M [t\rangle $$ - $$t$$ jest aktywne w $$M$$

#####Def.:
> Zbiór stanów osiągalnych w sieci $$N = <P, T, F>$$ ze stanu początkowego $$M$$, to najmniejszy zbiór $$[M]$$ spełniający warunki:  

 > - (1) $$M \in [M]$$ 
 > - (2) Jeśli $$M' \in [M] \wedge \exists_t : M' [t\rangle M''$$, to $$M'' \in [M]$$
 
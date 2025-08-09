![[Pasted image 20250225104002.png]]

#### Typisk opgave
Givet $A$ reel symmetrisk/normal. Find den spektrale dekomposition: $A = Q \land Q^T \Leftrightarrow A = U \land U^*$
1) Find alle egenværdier og egenvektorer  
$\lambda_1, \lambda_2, ..., \lambda_n$ (Opskrives med algebrarisk multiplicitet)
$$
\Lambda = \text{diag}(\lambda_1, \lambda_2, ..., \lambda_n)
$$
Ved tilfældet
$$
\Lambda = diag(1,2,2,2,5) \quad \text{ så er } \quad am(2)=3, am(1)=1, am(5)=1 \text{ samme for gm}
$$
I sådanne tilfælde skal vi kører Gram-Schmidt på (2,2,2) så vi får en korrekt værdi at bruge til $q_1$
1) Følg de to punkter
   * Hvis $\text{am}(\lambda_k) = 1$, normalisér den tilhørende egenvektor ([[Eigenværdi og Eigenvektor]]) og kald den $q_k$.
   * Hvis $\text{am}(\lambda_k) > 1$, kør Gram-Schmidt på dens lineært uafhængige egenvektorer. ($E_{\lambda_n}$)
2) Opstil egenvektormatricen $Q$:
$$
Q =
\begin{bmatrix}
| & | & & | \\
q_1 & q_2 & ... & q_n \\
| & | & & |
\end{bmatrix}
$$
Husk at rækkefølgen i $Q$skal passe til rækkefølgen i $\Lambda$.
#### FAKTABOKS
![[Pasted image 20250225110924.png]]
- Hvis $A$ er **reel symmetrisk** eller **Hermitisk**, så er egenværdierne **reelle**.  
- Ifølge k.t. 2.8.2, hvis $\lambda_k \neq \lambda_l$, så gælder:
$$
E_{\lambda_k} \perp E_{\lambda_l}
$$
- Hvis $A$ er **normal**, **Hermitisk** eller **reel symmetrisk**, så er egenvektorrummene for forskellige egenværdier **ortogonale**.
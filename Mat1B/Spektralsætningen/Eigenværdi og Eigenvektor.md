
Her er en oversigt over, hvordan man finder egenværdier og egenvektorer for en matrix både manuelt og ved hjælp af Python (sympy).

---
## Håndberegning
### 1. Bestem det karakteristiske polynomium
Givet en matrix **A**, skal du finde dens karakteristiske polynomium ved at sætte:
$$
det(A - \lambda I) = 0
$$
**Eksempel:**  
Lad
$$
A = 
\begin{bmatrix}
2 & 1 \\
1 & 2
\end{bmatrix}
$$
Beregn først **$A - \lambda I$**:
$$
A - \lambda I = 
\begin{bmatrix}
2 - \lambda & 1 \\
1 & 2 - \lambda
\end{bmatrix}
$$
Beregn determinanten:
$$
det(A - \lambda I) = (2 - \lambda )^2 - 1 = 0
$$
### 2. Løs for $\lambda$
Sæt ligningen op:
$$
(2 - \lambda )^2 - 1 = 0   \to   (2 - \lambda )^2 = 1
$$
Dette giver:
- Hvis **2 - $\lambda  = 1$**  →  **$\lambda  = 1$**
- Hvis **2 - $\lambda  = -1$** →  **$\lambda  = 3$**
### 3. Find egenvektorerne
For hver fundet egenværdi $\lambda$ løses ligningen:
$$
(A - \lambda I)v = 0
$$
**For $\lambda  = 1$:**  
Beregn **A - I**:
$$
A - I = 
\begin{bmatrix}
2 - 1 & 1 \\
1 & 2 - 1
\end{bmatrix}
= 
\begin{bmatrix}
1 & 1 \\
1 & 1
\end{bmatrix}
$$
Løs systemet:
$$
1 \cdot x + 1 \cdot y = 0  →  y = -x
$$En gyldig egenvektor kan være:
$$
v_1 = [1, -1]
$$
**For $\lambda  = 3$:**  
Beregn **A - 3I**:
$$
A - 3I = 
\begin{bmatrix}
2 - 3 & 1 \\
1 & 2 - 3
\end{bmatrix}
=
\begin{bmatrix}
-1 & 1 \\
1 & -1
\end{bmatrix}
$$
Løs systemet:
$$
-1 \cdot x + 1 \cdot y = 0  →  y = x
$$
En gyldig egenvektor kan være:
$$
v_2 = [1, 1]
$$
---
## Python Metode med sympy
Nedenfor er et eksempel på, hvordan du kan beregne egenværdier og egenvektorer for en matrix ved hjælp af sympy:

```python

import sympy as sp

  

# Definer matrixen

A = sp.Matrix([[2, 1],

               [1, 2]])

  

# Beregn egenværdier og egenvektorer

eigen_data = A.eigenvects()

  

# Udskriv resultaterne

for eigenval, multiplicity, eigenvec in eigen_data:

    print("Egenværdi:", eigenval)

    print("Egenvektor(er):")

    for vec in eigenvec:

        sp.pprint(vec)

    print()  # Blank linje til adskillelse

```
Dette script beregner og udskriver egenværdier og de tilhørende egenvektorer for matrix **A** ved hjælp af sympy.
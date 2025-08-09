# Noter om Matrix Typer
## Symmetrisk Matrix
- **Definition:** En matrix **A** er symmetrisk, hvis den er lig med sin transponerede.
  $$A = A^t$$
- **Bemærkning:** Dette betyder, at elementerne spejles omkring hoveddiagonalen.
## Hermitisk Matrix
- **Definition:** En matrix **A** er hermitisk (eller selv-adjungeret), hvis den er lig med sin hermitiske transponerede.
  $$A = A^*$$
- **Bemærkning:** Her betyder * den komplekse konjugerede transponering.
## Normal Matrix
- **Definition:** En matrix **A** er normal, hvis den kommuterer med sin hermitiske transponerede.
  $$AA^* = A^*A$$
- **Bemærkning:** Både reelle og komplekse matricer kan være normal, hvilket sikrer, at de kan diagonaliseres via en unitær transformation.
## Unitær Matrix
- **Definition:** En matrix **U** er unitær, hvis dens inverse er dens hermitiske transponerede.
  $$U^{-1} = U^*$$
- **Bemærkning:** Dette indebærer, at rækker og kolonner er ortonormale.
## Invertibel Matrix
- **Definition:** En matrix **A** er invertibel (eller ikke-singulær), hvis der findes en matrix **A⁻¹** sådan at:
  $$AA^{-1} = A^{-1}A = I$$
- **Bemærkning:** **I** er identitetsmatricen, og en invertibel matrix har en determinant, der er forskellig fra 0.
## Ortogonal Matrix
- **Definition:** En matrix **Q** er ortogonal, hvis dens inverse er lig med dens transponerede.  $$Q^{-1} = Q^T$$
- **Bemærkning:** Dette er en særlig type unitær matrix for reelle matricer, hvor rækker og kolonner danner et ortonormalt sæt.

# Supplemental Data for "Recommended DSMC Collision Model Parameters for Planetary Entry and Related Applications"

By Gosma, Swaminathan Gopalan, Subramaniam, and Stephani

## Contents

The repository contains the following files:

- **FULL_VSS_DATABASE.vss** - Full Collision-Specific VSS Database for atmospheric entry modeling applications containing 240 total species, fitted from 1000-20000 K.
- **Neutral_Low_T.vss** - Collision-Specific VSS Database for non-entry modeling applications containing 215 neutral species, fitted from 300-4000 K.
- **pirani.tran** - Full list of neutral species polarizability and effective electron values used in the computation of the phenomenological and Langevin potentials.
- **Pirani_Poly_Output.tran** - Phenomenological and Langevin Potential derived collision integral data for all possible neutral-neutral and neutral-ion combinations, fitted to Gupta Polynomial form from 300-20000 K.

Both VSS databases have been tested and are compatible with the latest public release of the SPARTA DSMC code [[1]](#references). Data sourcing and error statistics (when applicable) for each individual collision pair are provided.

The polarizability and effective electron values are provided roughly in the format required by the Mutation++ Library [[2]](#references). The source for each species is discussed in Section 2D of the manuscript. While not directly used in this work, the code can be readily used to compute the raw collision integral data used in this work, utilizing the same potential models. This may be useful for verification or additional transport-related work. The latter might includethe  computation of additional collision integral terms required for higher-order approximations of mixture transport values.

Using the Nelder-Mead optimization scheme described in the manuscript, "raw" collision integral data for all possible neutral-neutral and neutral-ion interactions were computed via the phenomenological and Langevin potentials, respectively, and fitted to the Gupta Polynomial Form [[3]](#references):

$$\left( \pi\overline{Ω}^{(1,1)}, \pi\overline{\Omega}^{(2,2)}, B^* \right) = D \cdot T^{\left[A(\ln(T))^2 + B(\ln(T)) + C\right]}$$

The resulting polynomial coefficients show good agreement, with an average error of less than 1% and a maximum error of less than 4% compared to the originally computed collision integral data.

## References

1. SPARTA DSMC Code - [https://sparta.sandia.gov](https://sparta.sandia.gov)
2. Scoggins, J. et al., Mutation++: An Open-Source Library for Chemical Kinetics and Transport Properties.
3. Gupta, R. N. et al., "Review of Reaction Rates and Thermodynamic and Transport Properties for the NASA Lewis Chemical Equilibrium Program," NASA TM-4513, 1990.

---
For further details, please refer to the full manuscript.


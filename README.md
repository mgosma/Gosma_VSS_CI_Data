# Gosma_VSS_CI_Data

Supplemental Data for "Recommended DSMC Collision Model Parameters for Planetary Entry and Related
Applications" by Gosma, Swaminathan Gopalan, Subramaniam, and Stephani.

At the time of manuscript review, the repo currently contains the following:

\begin{description}
\item [FULL\_VSS\_DATABASE.vss] Full Collision-Specific VSS Database for atmospheric entry modeling applications containing 240 total species, fitted from 1000-20000 K.
\item [Neutral\_Low\_T.vss] Collision-Specific VSS Database for non-entry modeling applications containing 215 neutral species, fitted from 300-4000 K.
\item [pirani.tran] Full list of neutral species polarizability and effective electron values used in the computation of the phenomenological and Langevin potentials.
\item [Pirani\_Poly\_Output.tran] Phenomenological and Langevin Potential derived collision integral data for all possible neutral-neutral and neutral-ion combinations, fitted to Gupta Polynomial form from 300-20000 K.
\end{description}

Both VSS databases have been tested and are compatible with the latest public release of the SPARTA DSMC code\cite{SPARTA}. Data sourcing and error statistics (when applicable) for each individual collision pair are provided.

The polarizability and effective electron values are provided roughly in the format required by the Mutation++ Library\cite{Scoggins2020}. The source for each species is discussed in Sec. 2D. While not directly used in this work, the code can be readily used to compute the raw collision integral data used in this work, utilizing the same potential models. This may be useful for verification or additional transport-related work. The latter might include computation of additional collision integral terms required for higher-order approximations of mixture transport values.

Using the same Nelder-Mead optimization scheme described in this work, "raw" collision integral data for all possible neutral-neutral and neutral-ion interactions were computed via the phenomenological and Langevin potentials respectively and fitted to Gupta Polynomial Form\cite{gupta_review_1990}:

\begin{equation}
(\pi\overline{\Omega}^{(1,1)}_{i,j}, \pi\overline{\Omega}^{(2,2)}_{i,j}, B^{*}_{i,j}) = 
D*T^{[A(ln(T))^2 + B(ln(T)) + C]}
\end{equation}

\noindent The resulting polynomial coefficients seem to be in good agreement, with an average error of less than 1\% and a maximum error of less than 4\% observed overall collision pairs compared to the originally computed collision integral data. While not directly used in this paper, these polynomials are provided for their potential use in CFD or CFD-DSMC hybrid applications.

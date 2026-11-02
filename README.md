# Path marking versus phase programming for programmable optical switching

Reproducible computations for the article *Path Marking versus Phase Programming for Programmable Optical Switching: Dominance, Classical Emulability and a Four-Path Witness*.

The notebook `marking_vs_phase.ipynb` compares two controls of multi-path interference at fixed path amplitudes: ideal path marking (coherence matrices that are positive semidefinite with unit diagonal) and phase programming, including any classical random-phase ensemble. It contains:

1. **Four-path witness.** A rank-two marking matrix $G_0$ realised with horizontal, vertical, diagonal and circular polarisation markers, and the projector $P$ onto its range. The collected fraction $\mathrm{tr}(PG)/4$ equals 1 for $G_0$. Its maximum over all fixed-amplitude phase ensembles is evaluated in closed form,
   $c^\star = \tfrac12 + \big[(4-\sqrt2)\sin(\pi/8) + (2+3\sqrt2)\cos(\pi/8)\big]/14 \approx 0.982642$,
   and confirmed globally by a branch-and-bound computation (double precision, tolerance $10^{-6}$).
2. **Far-field readout.** Reconstruction of $G_0$ from one simulated far-field image of four apertures with distinct baselines.
3. **Path-phase randomisation.** The collected fraction of the marked state, $1-\epsilon/2$, falls to $c^\star$ at $\epsilon \approx 3.5\%$.
4. **Exploratory survey** for 2 to 5 paths: semidefinite programming versus multi-start phase optimisation for random witnesses (candidate gaps only).

The notebook is stored with its text outputs. Results are written to `results/`:

| File | Content |
|---|---|
| `four_path_results.json` | Jones vectors, $c^\star$, maximising phases, branch-and-bound bound, margin, randomisation threshold, reconstruction error |
| `survey_results.json` | Survey statistics for $M=2,\dots,5$ (fixed seed) |
| `fig_m4_witness.pdf`, `.png` | Far-field pattern and witness versus randomisation (written when the notebook is run) |

## Running

Python 3.10 or later. The first cell installs `numpy`, `scipy`, `cvxpy` and `matplotlib` (versions in `requirements.txt`). Parts 1–3 run in about a minute; the survey takes several minutes. It runs unchanged in Google Colab.

## Scope

All results concern classical second-order coherence at fixed path amplitudes. The four-path construction follows Buscemi, Chiribella and D'Ariano, *Phys. Rev. Lett.* 95, 090501 (2005). The branch-and-bound bound is computer-assisted, without directed rounding. No experimental data are included.

## License

MIT (see `LICENSE`).

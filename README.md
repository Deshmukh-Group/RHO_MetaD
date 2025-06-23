# RHO_MetaD

Metadynamics simulations for the study: **"Polyacrylates with protein recognition and functional modulation"**.

This repository contains all relevant input files and scripts to run and analyze metadynamics simulations of polyacrylate sequences interacting with protein targets. The study investigates the influence of sequence composition and patterning on functional recognition using enhanced sampling techniques.

---

---

## 🔬 System Details

### Polymer Systems Simulated:

- **PEG**: Polyethylene glycol used as a control.
- **F1 (D5H8A5I5)**: Three sequence variants.
- **F8 (D2H7A5I8)**: Two sequence variants.

### Sequence Definitions:

#### F1 (D5H8A5I5)
- **Seq1**: `HDIHAHHIDAHDIDAHIAHDAHI`
- **Seq2**: `HIHIAAIHHDHHADIDHDIAADH`
- **Seq3**: `IHDHHAADHHADADDHIIIHAIH`

#### F8 (D2H7A5I8)
- **Seq1**: `IHIDHAHHIAHAIIHADIHIIA`
- **Seq2**: `IAAHHIHDIAAHIAIIIHIHHD`

---

## ⚙️ Simulation Details

Each system directory (e.g., `F1_V1/`, `F8_V1/`, etc.) includes:

- `index.ndx`: Index file for defining groups
- `md.mdp`: GROMACS input file with MD parameters
- `plumed.dat`: Configuration file for PLUMED, defining metadynamics settings including:
  - Collective variables (CVs)
  - Gaussian hill parameters
  - Bias reweighting
- `plumed_restart.dat`: Used for continuing metadynamics
- `production.tpr`: Precompiled GROMACS input binary
- `toppar/`: Directory with all relevant topology and force field files
  - `CLA.itp`, `SOD.itp`, `TIP3.itp`: Ions and water model
  - `LIG.itp`: Ligand/polymer parameters
  - `PROA.itp`: Protein topology
  - `forcefield.itp`: Base force field definitions

---

## 📊 Analysis Tools

Found in the `Analysis_Scripts/` folder:

- `analysis.py`: General post-processing pipeline
- `fes_2d.py`, `FES2D_Surf_normalized.py`: 2D Free Energy Surface generation
- `convergence_FES.py`: Evaluates FES convergence over time
- `find_minima_timeframe.py`: Locates time frames corresponding to FES minima
- `get_conformation_based_on_location.py`: Extracts representative structures from CV space
- `plot.sh`: Batch script for visualizing results

---

## 📦 Dependencies

- [GROMACS](https://www.gromacs.org/) (version used: 2022 or newer recommended)
- [PLUMED](https://www.plumed.org/) (v2.8+)
- Python 3.8+
  - `numpy`, `matplotlib`, `pandas`, `scipy`
  - Optional: `seaborn`, `MDAnalysis`

---

## 📜 Citation

If you use this repository or scripts in your work, please cite the associated publication:

> _Polyacrylates with protein recognition and functional modulation_, **Darwin C. Gomez, Swarnadeep Seth, Ronnie Mondal, Stephen J. Koehler, Jared G. Baker, Charles Plate, Ian C. Anderson, Mikayla R. Smith, Joey Gloriod, Morgan Gunter, Valerie Vaissier Welborn, Sanket A. Deshmukh, C. Adrian Figg**, Journal Name, Year. [DOI/link to be added when available]

---


## 🔖 License

This project is licensed under the MIT License. See the `LICENSE` file for details.




# HR-2R06-molecular-docking
Molecular docking HRV 2R06 with natural compounds
## Deskripsi Project

Proyek ini melakukan analisis **molecular docking** untuk menginvestigasi interaksi antara protein Human Rhinovirus 2R06 (HRV 2R06) dengan 5 senyawa bioaktif dari tanaman obat lokal Indonesia:

1. **Andrographolide** dari tanaman Sambiloto (Andrographis paniculata*)
2. **Baicalein** dari tanaman Bungli (*Scutellaria baicalensis*)
3. **Kaempferol** dari tanaman rimpang Kencur (*Kaempferia galanga*)
4. **Apigenin** dari tanaman Seledri (*Apium graveolens*)
5. **Quercetin** dari Sirsak (*Annona muricata*)

##Tujuan Project
Penelitian ini bertujuan untuk mengidentifikasi potensi inhibitor alami untuk virus rhinovirus melalui pendekatan *structure-bases drug discovery* menggunakan tanaman obat tradisional Indonesia.
1. Menganalisis potensi inhibitor HRV 2R06 dari 5 senyawa tanaman obat lokal
2. Membandingkan binding affinity andrographolide, baicalein, kaempferol, apigenin, dan quercetin
3. Mengidentifikasi mekanisme interaksi ligan-protein pada active site HRV 2R06
4. Menentukan senyawa dengan potensi tertinggi untuk pengembangan antiviral
5. Memberikan data scientific untuk validasi penggunaan tanaman obat tradisional

## Senyawa Uji (Ligand)

| No | Senyawa | Tanaman Lokal | Famili Kimia | MW | LogP | 
|----|---------|--------------|--------------|-----|------|
| 1 | Andrographolide | Sambiloto | Diterpenoid | 350.45 | 3.45 |
| 2 | Baicalein | Bungli | Flavone | 270.24 | 2.87 | 
| 3 | Kaempferol | Kencur | Flavonol | 286.24 | 1.38 |
| 4 | Apigenin | Seledri | Flavone | 270.24 | 2.13 | 
| 5 | Quercetin | Sirsak | Flavonol | 302.24 | 1.78 |

**Kriteria Pemilihan**
1. Bioaktivitas antiviral terbukti dari literatur
2. Ketersediaan dari tanaman obat tradisional Indonesia
3. Sifat kimia suitable untuk docking (Lipinski's Rule)
4. Potensi untuk pengembangan fitofarmaka

## 🔬 Tools & Software

Penelitian ini menggunakan perangkat lunak bioinformatika:

| Software | Versi | Fungsi |
|----------|-------|--------|
| **UCSF Chimera** | 1.x | Visualisasi struktur protein, preparasi ligand |
| **AutoDockTools** | 1.5.7 | Preparasi protein & grid mapping |
| **PyRx** | 0.9.x | Molecular docking otomatis |
| **PyMOL** | 2.x | Visualisasi dan analisis struktur |
| **DS Visualizer** | 3.x | Analisis interaksi detail (H-bonds, hydrophobic) |

---

## 📁 Struktur Direktori

```
├── README.md                          # Dokumentasi proyek
├── LICENSE                            # Lisensi proyek
├── .gitignore                         # File yang diabaikan
│
├── data/
│   ├── protein/
│   │   ├── 2R06.pdb                  # Struktur crystal protein HRV 2R06
│   │   └── 2R06_prepared.pdbqt       # Protein terpreparasi untuk docking
│   │
│   ├── ligands/
│   │   ├── natural_compounds/        # Senyawa dari tanaman obat lokal
│   │   │   ├── compound_001.mol2      # Format MOL2
│   │   │   ├── compound_002.pdb
│   │   │   └── ...
│   │   ├── ligands_prepared/         # Ligand terpreparasi (PDBQT)
│   │   │   ├── compound_001.pdbqt
│   │   │   └── ...
│   │   └── ligands_database.csv      # Katalog senyawa dengan properties
│   │
│   └── reference/                    # Data referensi
│       ├── known_inhibitors.pdb      # Inhibitor positif kontrol
│       └── docking_grid.gpf          # Grid parameter file
│
├── results/
│   ├── docking_results/
│   │   ├── compound_001_docking.dlg  # Docking log files
│   │   ├── compound_001_poses.pdb    # Pose hasil docking
│   │   └── ...
│   │
│   ├── binding_affinity/
│   │   ├── affinity_summary.csv      # Ringkasan ΔG untuk semua senyawa
│   │   ├── top_10_compounds.xlsx     # Senyawa dengan afinitas terbaik
│   │   └── affinity_distribution.png # Plot distribusi afinitas
│   │
│   ├── interaction_analysis/
│   │   ├── hydrogen_bonds.csv        # H-bond interactions
│   │   ├── hydrophobic_contacts.csv  # Hidrofobik interactions
│   │   └── salt_bridges.csv          # Ionic interactions
│   │
│   └── visualizations/
│       ├── top_compound_docking.pse  # PyMOL session files
│       ├── protein_ligand_complex.png
│       └── interaction_diagrams/     # Diagram 2D interaksi
│
├── scripts/
│   ├── 01_protein_preparation.py     # Script preparasi protein
│   ├── 02_ligand_preparation.py      # Script preparasi ligand
│   ├── 03_docking_execution.py       # Script running docking
│   ├── 04_results_analysis.py        # Analisis binding affinity
│   ├── 05_interaction_analysis.py    # Analisis interaksi detail
│   ├── utils/
│   │   ├── pdb_utils.py              # Utility fungsi PDB parsing
│   │   ├── docking_utils.py          # Utility untuk docking
│   │   └── visualization_utils.py    # Fungsi plotting & visualisasi
│   └── requirements.txt               # Python dependencies
│
├── notebooks/
│   ├── 01_Data_Exploration.ipynb           # EDA struktur protein & ligand
│   ├── 02_Docking_Workflow.ipynb           # Pipeline docking lengkap
│   ├── 03_Results_Analysis.ipynb           # Analisis hasil docking
│   ├── 04_Binding_Affinity_Analysis.ipynb  # Analisis afinitas binding
│   └── 05_Visualization_Interactive.ipynb  # Visualisasi interaktif
│
├── docs/
│   ├── METHODOLOGY.md                # Metodologi penelitian
│   ├── INSTALLATION.md               # Panduan instalasi tools
│   ├── USAGE_GUIDE.md                # Panduan penggunaan
│   ├── RESULTS_INTERPRETATION.md     # Interpretasi hasil
│   └── REFERENCES.md                 # Referensi publikasi
│
└── figures/
    ├── workflow_diagram.png          # Diagram alur kerja
    ├── protein_structure.png         # Gambar struktur protein
    └── top_docking_poses.png         # Pose terbaik untuk publikasi
```

---

## 🚀 Cara Memulai

### Prasyarat
- Python 3.8+
- UCSF Chimera (https://www.cgl.ucsf.edu/chimera/)
- AutoDockTools 
- PyRx 
- PyMOL 
- DS Visualizer 

### Instalasi

1. **Clone repository:**
```bash
git clone https://github.com/username/hrv-2r06-molecular-docking.git
cd hrv-2r06-molecular-docking
```

2. **Setup Python environment:**
```bash
python -m venv venv
source venv/bin/activate  # Di Windows: venv\Scripts\activate
pip install -r scripts/requirements.txt
```

3. **Download struktur protein:**
```bash
# PDB ID: 2R06 dapat diunduh dari RCSB PDB
# https://www.rcsb.org/structure/2R06
```

4. **Ikuti dokumentasi instalasi tools:**
```bash
cd docs
# Baca INSTALLATION.md untuk petunjuk detail
```

---

## 📊 Workflow Docking

```
┌─────────────────────────────────────────────────────────────┐
│                     DATA PREPARATION                        │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  1. Download struktur 2R06 dari RCSB PDB                    │
│     └─> UCSF Chimera: Cleaning struktur                     │
│                                                             │
│  2. Preparasi Protein (AutoDockTools)                       │
│     └─> Add polar hydrogens                                 │
│     └─> Assign Gasteiger charges                            │
│     └─> Convert to PDBQT format                             │
│                                                             │
│  3. Preparasi Ligand (PyRx/AutoDockTools)                   │
│     └─> 3D coordinate generation                            │
│     └─> Rotatable bonds identification                      │
│     └─> Assign charges                                      │
│     └─> Convert to PDBQT format                             │
│                                                             │
│  4. Define Docking Grid (AutoDockTools)                     │
│     └─> Tentukan active site                                │
│     └─> Set grid parameters (.gpf)                          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────────┐
│                  MOLECULAR DOCKING                          │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  5. Run Docking (PyRx)                                      │
│     └─> AutoDock Vina algorithm                             │
│     └─> Generate poses & binding energies (ΔG)              │
│                                                             │
└─────────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────────┐
│                RESULTS ANALYSIS                             │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  6. Binding Affinity Analysis (Python scripts)              │
│     └─> Compare ΔG values                                   │
│     └─> Rank compounds                                      │
│     └─> Statistical analysis                                │
│                                                             │
│  7. Interaction Analysis (DS Visualizer)                    │
│     └─> H-bond networks                                     │
│     └─> Hydrophobic contacts                                │
│     └─> Van der Waals interactions                          │
│     └─> Salt bridges                                        │
│                                                             │
│  8. Visualization (PyMOL, Chimera)                          │
│     └─> 3D complex structure                                │
│     └─> Interaction diagrams                                │
│     └─> Publication-ready figures                           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 🔍 Key Results

### Binding Affinity Summary

| No | Compound | ΔG (kcal/mol) | RMSD (Å) | Hydrogen Bonds | 
|----|---------:|:-------------:|:--------:|:--------------:|
| 1 | Andrographolide | -7.1 | 0 | 2 | 
| 2 | Baicalein | -8.1 | 0 | 3 |
| 3 | Kaempferol | -8.1 | 0 | 5 |
| 4 | Apigenin | -10 | 0 | 7 |
| 5 | Quercetin | -5.7 | 0 | 1 |

*ΔG: Binding Free Energy (lebih negatif = lebih kuat)*

### Top 3 Compounds
- **Apigenin**: ΔG = -10 kcal/mol
- **Kaempferol**: ΔG = -8.1 kcal/mol
- **Baicalein**: ΔG = -8.1 kcal/mol

---

## 📚 Dokumentasi Lengkap

Untuk dokumentasi detail, silakan baca:

- **[METHODOLOGY.md](docs/METHODOLOGY.md)** - Metodologi penelitian dan protokol docking
- **[INSTALLATION.md](docs/INSTALLATION.md)** - Panduan instalasi semua tools
- **[USAGE_GUIDE.md](docs/USAGE_GUIDE.md)** - Cara menggunakan scripts dan notebooks
- **[RESULTS_INTERPRETATION.md](docs/RESULTS_INTERPRETATION.md)** - Interpretasi hasil docking
- **[REFERENCES.md](docs/REFERENCES.md)** - Literatur dan publikasi terkait

---

## 💻 Scripts & Notebooks

### Python Scripts
```bash
# Menjalankan protein preparation
python scripts/01_protein_preparation.py --input data/protein/2R06.pdb

# Menjalankan ligand preparation
python scripts/02_ligand_preparation.py --ligands data/ligands/natural_compounds/

# Menjalankan docking
python scripts/03_docking_execution.py --protein data/protein/2R06_prepared.pdbqt

# Analisis results
python scripts/04_results_analysis.py --results results/docking_results/

# Interaction analysis
python scripts/05_interaction_analysis.py --complex results/docking_results/
```

### Jupyter Notebooks
```bash
# Jalankan Jupyter
jupyter notebook notebooks/

# Buka notebook untuk explorasi dan visualisasi
# - 01_Data_Exploration.ipynb
# - 02_Docking_Workflow.ipynb
# - 03_Results_Analysis.ipynb
# - 04_Binding_Affinity_Analysis.ipynb
# - 05_Visualization_Interactive.ipynb
```

---

## 📊 Dependencies

Python packages yang digunakan:

```
biopython==1.83
pandas==2.0.0
numpy==1.24.0
matplotlib==3.7.0
seaborn==0.12.0
scipy==1.10.0
rdkit==2023.03.1
jupyter==1.0.0
ipython==8.12.0
plotly==5.13.0
```

Lihat `scripts/requirements.txt` untuk informasi lengkap.

---


---

## 🤝 Kontribusi

Kami terbuka untuk kontribusi! Jika Anda memiliki:
- Senyawa baru untuk dianalisis
- Perbaikan metodologi
- Bug fixes atau optimisasi code
- Hasil docking tambahan

Silakan:
1. Fork repository ini
2. Buat branch fitur (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push ke branch (`git push origin feature/AmazingFeature`)
5. Buat Pull Request

---

## 🔗 Referensi Berguna

### Tools & Software
- [RCSB PDB Database](https://www.rcsb.org/) - Download struktur protein
- [UCSF Chimera Documentation](https://www.cgl.ucsf.edu/chimera/)
- [AutoDock Vina](http://vina.scripps.edu/)
- [PyMOL Documentation](https://pymol.org/)

### Database Senyawa
- [PubChem](https://pubchem.ncbi.nlm.nih.gov/)
- [ChemSpider](https://www.chemspider.com/)
- [Traditional Medicine Database](http://www.dddc.ac.cn/) (untuk senyawa tradisional)

### Publikasi Terkait
- Morris et al. (2009). AutoDock4 and AutoDockTools
- Trott & Olson (2010). AutoDock Vina
- [Lihat REFERENCES.md](docs/REFERENCES.md) untuk daftar lengkap

---

## 📝 Changelog

### Version 1.0 (2024-05-23)
- ✅ Initial repository setup
- ✅ Protein preparation workflow
- ✅ Ligand preparation for docking
- ✅ Docking execution scripts
- ✅ Binding affinity analysis
- ✅ Interaction analysis tools
- ✅ Visualization utilities


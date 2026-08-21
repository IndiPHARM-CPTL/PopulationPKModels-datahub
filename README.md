# PopulationPKModels-datahub
Pharmacokinetic modeling and simulation - IndiPHARM
<div align="center">

🧬 PopulationPKModels-datahub
IndiPHARM-CPTL · Columbia University
</div>

### ✨ What is this repository?

PopulationPKModels-datahub is a living collection of literature-derived population pharmacokinetic (PopPK) models.

🔎 Review — examine the structural model, parameters, and covariates;

♻️ Modeling — rebuild concentration–time profiles from published model;

🧪 Simulation — generate single-patient and population-level PK profiles across dosing regimens;

📊 Comparison — evaluate exposure and variability across drugs and therapeutic classes;

🧠 Extension — connect PK models with pharmacodynamics, biomarkers, assays, and patient-level data.

🗂️ This repository is under active development. 

### 🧭 Repository map - PopulationPKModels-datahub

Additional therapeutic areas and model classes will be incorporated as the data hub expands.

🩸 Hyperlipidemia

❤️ Hypertension

🍬 T2DM

🎯 Immunosuppressants

🧠 Neuropsychiatric Drugs

### 🚀 Quick start

### 1. Clone the repository

git clone https://github.com/IndiPHARM-CPTL/PopulationPKModels-datahub.git
cd PopulationPKModels-datahub

### 2. Install common R dependencies

install.packages(c(
  "mrgsolve"
))

(Individual models may require additional packages.)

### 3. Navigate to a therapeutic area

Browse available therapeutic-area models in the repository.

### 💻 Example simulation

See the standardized simulation workflow in [`SimulationBackbone`](./SimulationBackbone).

### 📈 Example outputs

Example concentration–time profiles and simulation outputs are available in [`SimulationBackbone`](./SimulationBackbone).

### 🤝 Contributing

Contributions that improve model accuracy, documentation, validation, or reproducibility are welcome.

Useful contributions include:

➕ adding a published PopPK model;

🧮 correcting equations or parameterization;

📝 improving documentation;

📚 adding missing literature provenance;

📊 adding validation figures;

🧪 testing alternative simulation scenarios;

🐛 reporting implementation errors.

For substantial additions or model changes, please open an Issue before submitting a pull request.

### 📬 Contact

For broader questions regarding the repository, research collaboration, or IndiPHARM-CPTL, please contact:

**Merilyn Xie**  
Postdoctoral Research Scientist  
Columbia University  
IndiPHARM-CPTL

📧 `mhx2000@cumc.columbia.edu`

### 📖 Citation

If you use a model from this repository in research, please cite:

1. the original publication describing the population PK model; and 

2. this repository.

```
Xie MH, Lacroix M, Rodda R, Lyashchenko AK, Cremers S. *PopulationPKModels-datahub: Reproducible population pharmacokinetic models for precision pharmacology*. IndiPHARM-CPTL; 2026. GitHub repository.
```

### ⚠️ Disclaimer

This repository is intended for academic use only. It is not intended for clinical decision-making.


### About IndiPHARM-CPTL

🌐 IndiPHARM 

https://arpa-h.gov/explore-funding/awards/1701

https://www.publichealth.columbia.edu/research/centers/center-innovative-exposomics/research/indipharm

🧬 CPTL 

https://www.pathology.columbia.edu/diagnostic-specialties/laboratory-medicine-division/clinical-pharmacology-and-toxicology-laboratory

🧩 IndiPHARM-CPTL / PopulationPKModels-datahub

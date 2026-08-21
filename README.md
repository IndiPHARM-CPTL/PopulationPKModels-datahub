# PopulationPKModels-datahub
Pharmacokinetic modeling and simulation - IndiPHARM
<div align="center">

🧬 PopulationPKModels-datahub
IndiPHARM-CPTL · Columbia University
</div>

✨ What is this repository?

PopulationPKModels-datahub is a living collection of literature-derived population pharmacokinetic (PopPK) models.

🔎 Review — examine the structural model, parameters, and covariates;

♻️ Modeling — rebuild concentration–time profiles from published model;

🧪 Simulation — generate single-patient and population-level PK profiles across dosing regimens;

📊 Comparison — evaluate exposure and variability across drugs and therapeutic classes;

🧠 Extension — connect PK models with pharmacodynamics, biomarkers, assays, and patient-level data.

🗂️ This repository is under active development. 



🎯 Repository map - PopulationPKModels-datahub/
🩸 Hyperlipidemia

❤️ Hypertension

🍬 T2DM

🧩 Additional therapeutic areas and model classes will be incorporated as the data hub expands.

🚀 Quick start

1. Clone the repository

git clone https://github.com/IndiPHARM-CPTL/PopulationPKModels-datahub.git
cd PopulationPKModels-datahub

2. Install common R dependencies

install.packages(c(
  "mrgsolve"
))

(Individual models may require additional packages.)

3. Navigate to a therapeutic area

💻 Example simulation

A simplified mrgsolve workflow may look like:

library(mrgsolve)
library(dplyr)
library(ggplot2)

mod <- mread(
  "model_name",
  "path/to/model"
)

dose <- ev(
  time = 0,
  amt  = 10,
  cmt  = 1
)

sim <- mod |>
  ev(dose) |>
  mrgsim(
    end   = 48,
    delta = 0.1
  ) |>
  as_tibble()

ggplot(sim, aes(time, CP)) +
  geom_line() +
  labs(
    x = "Time",
    y = "Concentration",
    title = "Simulated concentration–time profile"
  )

📋 Model documentation 

Field

Drug

Therapeutic area

Disease or indication

Primary PopPK publication

Study population

Structural model

Parameter estimates

Fixed effects

Random effects

IIV and RSC

Covariates (Weight, renal function, genotype, disease state, etc.)

Dosing regimen (Route, amount, dose interval)

Simulation and reference settings

Comparison with reported PK behavior

Limitations



A drug-specific README.md should ideally include:

Drug and indication

Source publication

Study population

Structural PK model

Fixed-effect parameters

Interindividual variability

Residual error model

Covariate relationships

Dosing regimen

Simulation assumptions

Reproduction of published results

Known limitations


📈 Example outputs

🌐 

🤝 Contributing

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

📬 Contact

For broader questions regarding the repository, research collaboration, or IndiPHARM-CPTL, please contact:

**Merilyn Xie**  
Postdoctoral Research Scientist  
Columbia University  
IndiPHARM-CPTL

📧 `mhx2000@cumc.columbia.edu`

📖 Citation

If you use a model from this repository in research, please cite:

the original publication describing the population PK model; and

this repository and an associated IndiPHARM publication.

⚠️ Disclaimer

[!WARNING]
This repository is intended for academia use only. It is not intended for clinical decision-making.


🧭 Roadmap


🧬 About IndiPHARM-CPTL

IndiPHARM https://arpa-h.gov/explore-funding/awards/1701
https://www.publichealth.columbia.edu/research/centers/center-innovative-exposomics/research/indipharm
CPTL https://www.pathology.columbia.edu/diagnostic-specialties/laboratory-medicine-division/clinical-pharmacology-and-toxicology-laboratory
IndiPHARM-CPTL / PopulationPKModels-datahub

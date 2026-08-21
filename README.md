# PopulationPKModels-datahub
Pharmacokinetic modeling and simulation - IndiPHARM
<div align="center">

🧬 PopulationPKModels-datahub
IndiPHARM-CPTL · Columbia University
</div>

✨ What is this repository?

PopulationPKModels-datahub is a living collection of literature-derived population pharmacokinetic (PopPK) models.

🔎 review — examine the structural model, parameters, and covariates;

♻️ reproduce — rebuild concentration–time profiles from published model;

🧪 simulate — generate single-patient and population-level PK profiles across dosing regimens;

📊 compare — evaluate exposure and variability across drugs and therapeutic classes;

🧠 extend — connect PK models with pharmacodynamics, biomarkers, assays, and patient-level data.

[!NOTE]
This repository is under active development. Model coverage, documentation, and validation materials are being expanded iteratively.

🎯 Project vision

Published PopPK models are often scattered across manuscripts, supplements, software formats, and study-specific implementations. Even when a model is technically reproducible, substantial work may be required before it can be reused for a new scientific question.

This repository aims to provide a common bridge between:

Published PopPK model
        ↓
Reconstructed executable model
        ↓
Standardized simulation workflow
        ↓
Exposure + variability summaries
        ↓
PK/PD, biomarker, and precision-pharmacology applications

The long-term goal is not simply to archive models, but to develop a reusable model infrastructure for studying treatment variability and model-informed pharmacotherapy.

🗂️ Repository map

PopulationPKModels-datahub/
│
├── 🩸 Hyperlipidemia/
│   └── literature-derived lipid-lowering drug models
│
├── ❤️ Hypertension/
│   └── antihypertensive and cardiovascular drug models
│
├── 🍬 T2DM/
│   └── non-insulin antihyperglycemic drug models
│
└── 📘 README.md

Additional therapeutic areas and model classes will be incorporated as the data hub expands.

🧩 Standard modeling workflow

Each model is developed through a common workflow whenever the source publication provides sufficient information.

flowchart LR
    A[Identify published PopPK model] --> B[Extract structural model]
    B --> C[Extract parameters & covariates]
    C --> D[Implement executable model]
    D --> E[Simulate typical subject]
    E --> F[Simulate population variability]
    F --> G[Generate PK summaries]
    G --> H[Compare with published results]
    H --> I[Extend to PK/PD or precision pharmacology]

1. Literature model identification

A published population PK model is selected based on scientific relevance and reproducibility of the reported model specification.

2. Model reconstruction

The published structural model, fixed effects, interindividual variability, residual error, and covariate relationships are translated into executable code.

3. Typical-subject simulation

A reference patient or representative covariate set is used to generate an interpretable baseline concentration–time profile.

4. Population simulation

When variability parameters are available, virtual populations are generated to characterize expected between-subject variability.

5. Exposure characterization

Common PK outputs 

6. Model Comparison

🛠️ Core computational stack

<div align="center">

Tool

Role

R

Data processing, simulation workflows, visualization

mrgsolve

ODE-based PK model implementation and simulation

dplyr / tidyr

Data transformation

ggplot2

Concentration–time and variability visualization

Git / GitHub

Version control, model provenance, reproducibility

</div>

🚀 Quick start

1. Clone the repository

git clone https://github.com/IndiPHARM-CPTL/PopulationPKModels-datahub.git
cd PopulationPKModels-datahub

2. Install common R dependencies

install.packages(c(
  "mrgsolve"
))

Individual models may require additional packages.

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

Missing information or assumptions introduced during reconstruction

🧪 Therapeutic areas

🍬 Type 2 Diabetes Mellitus

❤️ Hypertension

🩸 Hyperlipidemia


A drug-specific README.md should ideally include:

<details>
<summary><b>Suggested model README sections</b></summary>

<br>

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

</details>

📈 Example outputs

🌐 From PopPK to precision pharmacology

The broader scientific framework of the project is:

flowchart TD
    A[Drug dose] --> B[Population PK]
    B --> C[Individual exposure]
    C --> D[Biomarkers / assays]
    C --> E[Pharmacodynamic response]
    D --> F[Patient-specific interpretation]
    E --> F
    F --> G[Model-informed treatment optimization]

This enables the model library to function as more than a static repository: it can serve as a computational foundation for studying why patients receiving the same therapy may experience different exposures and outcomes.

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

New-model checklist

When contributing a new model, please provide:

Original publication citation

Study population

Structural model description

Fixed-effect parameter estimates

Random-effect / residual-error terms

Covariate relationships

Dose and route

Simulation assumptions

Executable implementation

Validation or reproduction notes

Known limitations

📖 Citation

If you use a model from this repository in research, please cite:

the original publication describing the population PK model; and

this repository and an associated IndiPHARM publication.

⚠️ Intended use and disclaimer

[!WARNING]
This repository is intended for academia use only. It is not intended for clinical decision-making.


🧭 Roadmap


🧬 About IndiPHARM-CPTL





<div align="center">

PopulationPKModels-datahub

From published models → reproducible simulations → precision pharmacology

IndiPHARM-CPTL / PopulationPKModels-datahub

</div>

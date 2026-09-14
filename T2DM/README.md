# Type 2 Diabetes Mellitus (T2DM)

This directory contains pharmacokinetic modeling resources for medications used in the management of **type 2 diabetes mellitus (T2DM)**.

The models are organized by therapeutic class and are intended to support the reconstruction, simulation, comparison, and evaluation of published pharmacokinetic models across non-insulin antihyperglycemic therapies.

> **Repository:** PopulationPKModels-datahub  
> **Therapeutic area:** Type 2 Diabetes Mellitus  
> **Modeling framework:** Population pharmacokinetics / pharmacokinetic-pharmacodynamic modeling

---

## Drug Classes

| Drug Class | Examples | Directory |
|---|---|---|
| **α-Glucosidase Inhibitors** | Acarbose, miglitol, voglibose | [Alpha-Glucosidase Inhibitors](./Alpha-Glucosidase%20Inhibitors/) |
| **Biguanides** | Metformin | [Biguanide](./Biguanide/) |
| **Bile Acid Sequestrants** | Colesevelam | [Bile Acid Sequestrants](./Bile%20Acid%20Sequestrants/) |
| **DPP-4 Inhibitors** | Sitagliptin, saxagliptin, linagliptin, alogliptin | [DPP4 inhibitors](./DPP4%20inhibitors/) |
| **Dopamine-2 Agonists** | Bromocriptine | [Dopamine-2 Agonist](./Dopamine-2%20Agonist/) |
| **GLP-1 Receptor Agonists** | Semaglutide, liraglutide, dulaglutide, exenatide | [GLP1](./GLP1/) |
| **Meglitinides** | Repaglinide, nateglinide | [Meglitinide](./Meglitinide/) |
| **SGLT2 Inhibitors** | Empagliflozin, dapagliflozin, canagliflozin, ertugliflozin | [SGLT2 inhibitors](./SGLT2%20inhibitors/) |
| **Sulfonylureas** | Glimepiride, glipizide, glyburide | [Sulfonylureas](./Sulfonylureas/) |
| **Thiazolidinediones** | Pioglitazone, rosiglitazone | [Thiazolidinediones](./Thiazolidinediones/) |

---

## Repository Structure

Each therapeutic-class directory contains drug-specific modeling resources derived from published pharmacokinetic literature.

Depending on the availability of published models and source data, individual drug folders may contain:

- Published PopPK, PK/PD, or related pharmacometric model implementations
- Model parameterization and covariate information
- Simulation scripts
- Typical population simulations
- Variability simulations
- Exposure metrics such as:
  - AUC
  - Cmax
  - Tmax
  - Ctrough
- Supporting references and model documentation
- Figures and tabulated simulation outputs

The structure of individual drug folders may vary depending on the complexity of the published model and the availability of sufficient information for model reconstruction.

---

## Model Reconstruction

Published models are evaluated before reconstruction to determine whether sufficient information is available to reproduce the reported pharmacokinetic behavior.

Model reconstruction may include:

1. Structural pharmacokinetic model
2. Fixed-effect parameter estimates
3. Interindividual variability
4. Residual unexplained variability, when applicable
5. Covariate relationships
6. Dosing regimen
7. Population characteristics
8. Formulation and route of administration

When multiple models are available for the same drug, models may be compared according to their clinical relevance, population characteristics, model completeness, and suitability for simulation.

---

## Simulation Framework

Models in this repository are primarily implemented using **R** and **mrgsolve**.

Where appropriate, simulations may include:

### Typical-subject simulation
Simulation using the reported typical population parameter estimates.

### Population simulation
Virtual-population simulations incorporating reported interindividual variability.

### Multiple-dose simulation
Repeated-dose simulation to characterize accumulation and steady-state exposure.

### Exposure summaries
PopPK models could derive the following common PK endpoints include:

| Metric | Description |
|---|---|
| **Cmax** | Maximum plasma concentration |
| **Tmax** | Time to maximum plasma concentration |
| **Ctrough** | Concentration immediately before the subsequent dose |
| **AUC** | Area under the curve |

---

## Supporting Drug Information

Additional files summarize drug-specific characteristics.

### Drug-level reference tables

- **[Drug List 1 – Enzymes and Transporters](./Drug%20list%201%20-%20enzymes%2C%20transporters.xlsx)**  

- **[Drug List 2 – Metabolites and Renal/Hepatic Elimination](./Drug%20list%202%20-%20metabolites%20and%20renal%20elimination.xlsx)**


---

## Intended Use

This repository is designed as a **research and pharmacometric resource** for:

- Population pharmacokinetic model reconstruction
- Model comparison
- Pharmacokinetic modeling and simulation
- Drug Exposure assessment
- Model-informed precision dosing related research
- Therapeutic drug monitoring and PK/PD related research

The repository is intended for **research and educational purposes** and should not be used as prescribing information or independent clinical decision-making.

---

## Contributing

Contributions and comments that could improve our models are welcome.

Examples include:

- Additional published PopPK models
- Corrections to reconstructed model parameters
- Additional validation datasets
- Improved model documentation
- Updated pharmacokinetic literature

---

## Citation

If you use models or data from this repository in academic work, please cite the original pharmacokinetic publication associated with each model in addition to citing this repository where appropriate.

---

## Authors

**Merilyn H. Xie**   (mhx2000@cumc.columbia.edu)

**Mathilde Lacroix**  
**Ramesh Rodda**  
**Alex K. Lyashchenko**  
**Serge Cremers**

Columbia University Irving Medical Center  
Clinical Pharmacology and Toxicology Laboratory
CPTL@cumc.columbia.edu
---

## Disclaimer

The models in this repository are reconstructions of published pharmacokinetic models and are provided for research purposes only. 

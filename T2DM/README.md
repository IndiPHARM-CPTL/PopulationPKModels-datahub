# Type 2 Diabetes Mellitus (T2DM)

This page directs PK modeling resources for medications commonly used in the management of type 2 diabetes mellitus (T2DM). The models in this database are grouped by therapeutic class and reconstructed according to the published PK models.

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

## Model Reconstruction

Published models were evaluated to determine whether sufficient information was sufficient for model reconstruction.

Model reconstruction may include:

1. Structural PK model
2. PK(/PD) parameter estimates
3. IIV
4. RSV
5. Covariate
6. Dosing regimen (for simulation, according to disease types)
7. Patient population baseline characteristics
8. Drug formulation and route of administration

---

## Simulation Framework

### Simulation with population mean 
Using the reported population PK parameter estimates.

### Population simulation
Virtual population simulations with reported IIV.

### Multiple-dose simulation
Multiple ascending dose simulation to characterize accumulation and steady-state exposure.

### Simulation results

| Metric | Description |
|---|---|
| **Cmax** | Maximum plasma concentration |
| **Tmax** | Time to maximum plasma concentration |
| **Ctrough** | Concentration before the next dose |
| **AUC** | Area under the curve |


---

## Intended Use

This repository is designed as a **research and pharmacometric resource** for:

- Population PK model reconstruction
- Model comparison for selected drugs such as metformin
- PK modeling and simulation
- MIPD (Model-informed precision dosing)-related research
- TDM (therapeutic drug monitoring) research and future patient care

The repository is intended for **research and educational purposes** and should not be used as prescribing information or independent clinical decision-making.

---

## Contributing

We welcome contributions, comments, and constructive critiques that could help improve our database.

---

## Citation

If you use models or data from this repository in academic work, please cite the original publication in addition to citing this repository.

---

## Authors

**Merilyn H. Xie  (mhx2000@cumc.columbia.edu)**  
**Mathilde Lacroix**  
**Ramesh Rodda**  
**Alex K. Lyashchenko**  
**Serge Cremers**

**Clinical Pharmacology and Toxicology Laboratory (CPTL@cumc.columbia.edu)**

**Columbia University Irving Medical Center**  

---

## Disclaimer

The models in this repository are reconstructions of published pharmacokinetic models and are provided for research purposes only. 

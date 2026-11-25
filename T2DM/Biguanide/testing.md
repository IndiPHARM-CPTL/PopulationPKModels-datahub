# **Metformin – Hong et al. (2008)**

**Drug class:** Biguanide

**Model type:** Population pharmacokinetic (PopPK) model

**Patient population:** Patients with type 2 diabetes mellitus (T2DM)

**Model implementation:** R (mrgsolve), NONMEM

## **Reference**

Hong Y, Rohatagi S, Habtemariam B, Walker JR, Schwartz SL, Mager DE.
Population exposure-response modeling of metformin in patients with
type 2 diabetes mellitus. J Clin Pharmacol. 2008;48(6):696–707.
DOI: [10.1177/0091270008316884](https://doi.org/10.1177/0091270008316884)

## **Structural Model**

- One-compartment model; First-order absorption, first-order elimination

## **Population PK Parameters**

| Parameter | Description | Estimate | Unit |
|---|---|---:|---|
| KA | Absorption rate constant | 2.15 | h⁻¹ |
| CL/F | Apparent clearance | 79.1 | L/h |
| V/F | Apparent volume of distribution | 643 | L |
| POW | Power coefficient of CLCR on CL/F | 0.822 | — |
| REF_CLCR | Reference creatinine clearance | 100 | mL/min |

## **Covariates**

| Covariate | Associated PK Parameter | Relationship |
|---|---|---|
| Creatinine clearance (CLCR) | CL/F | Power function |

Individual clearance is calculated as:

$$
CL_i = 79.1 \times \left(\frac{CLCR_i}{100}\right)^{0.822}
\times e^{\eta_{CL}}
$$

## **Interindividual Variability (IIV)**

| Parameter | Variance (ω²) |
|---|---:|
| KA | 0.29 |
| CL/F | 0.05 |
| V/F | 0.17 |

## **Model Implementation**

The published PK model was implemented in R using the mrgsolve
package to support single-dose and multiple-dose simulations,
population concentration-time profiles, and model-informed
interpretation of systemic metformin exposure.

The simulated plasma concentrations are expressed in ng/mL.

## **R Code**

```r


```

## **Model Scope**

This model only describes the PK portion of the original publication. The PK/PD part is attached below.

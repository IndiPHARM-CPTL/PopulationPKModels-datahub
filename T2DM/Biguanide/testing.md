# **Metformin – Hong et al. (2008)**

**Drug class:** Biguanide

**Model type:** Population pharmacokinetic (PopPK) model

**Patient population:** Patients with type 2 diabetes mellitus (T2DM)

**Model implementation:** R (mrgsolve)

## **Reference**

Hong Y, Rohatagi S, Habtemariam B, Walker JR, Schwartz SL, Mager DE.
Population exposure-response modeling of metformin in patients with
type 2 diabetes mellitus. J Clin Pharmacol. 2008;48(6):696–707.

DOI: [10.1177/0091270008316884](https://doi.org/10.1177/0091270008316884)

## **Structural Model**

- One-compartment model
- First-order absorption
- First-order elimination
- Oral administration

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

Interindividual variability is implemented using exponential random effects.

## **Residual Unexplained Variability (RUV)**

Combined additive and proportional residual error model.

## **Model Implementation**

The published PK model was implemented in R using the mrgsolve
package to support single-dose and multiple-dose simulations,
population concentration-time profiles, and model-informed
interpretation of systemic metformin exposure.

The simulated plasma concentrations are expressed in ng/mL.

## **R Code**

```r
# Insert the model implementation here
```

## **Model Scope**

This implementation describes the pharmacokinetic component of the
original publication. The pharmacodynamic exposure-response component
is not included in the current implementation.

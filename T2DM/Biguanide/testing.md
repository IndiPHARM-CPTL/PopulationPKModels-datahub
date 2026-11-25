# **Metformin – Hong et al. (2008)**

**Drug class:** Biguanide

**Model type:** Population pharmacokinetic (PopPK) model derived from PK/PD model 

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

## **Model Reconstruction and Simulation**

The Hong PK model was reproduced based on the reported PK parameters in R with the mrgsolve package for single-dose and multiple-dose simulations, population concentration-time profiles, and model-informed derivation of systemic metformin exposure.

## **NONMEM Code**
```NONMEM
$PROBLEM METFORMIN PK MODEL
Hong Y, Rohatagi S, Habtemariam B, Walker JR, Schwartz SL, Mager DE. J Clin Pharmacol. 2008;48(6):696-707.

$INPUT ID TIME AMT DV EVID MDV CMT RATE CLCR

$DATA metformin_nonmem.csv IGNORE=@

$SUBROUTINES ADVAN2 TRANS2

$PK
TVKA   = THETA(1)
TVCL   = THETA(2)
TVV    = THETA(3)
POW    = THETA(4)

REFCLCR = 100

KA = TVKA*EXP(ETA(1))
CL = TVCL*(CLCR/REFCLCR)**POW*EXP(ETA(2))
V  = TVV*EXP(ETA(3))

; Scale central compartment to concentration in mg/L
S2 = V

$ERROR
IPRED = F*1000

Y = IPRED*(1 + EPS(2)) + EPS(1)

IRES = DV - IPRED
W = SQRT(SIGMA(1,1) + IPRED*IPRED*SIGMA(2,2))
IF (W.EQ.0) W = 1
IWRES = IRES/W

$THETA
(0, 2.15)    ; KA (1/h)
(0, 79.1)    ; CL/F (L/h)
(0, 643)     ; V/F (L)
(0, 0.822)   ; POW effect of CLCR on CL

$OMEGA
0.29 ; ETA_KA
0.052 ; ETA_CL
0.167; ETA_V

$SIGMA
209          ; additive error variance
6.12         ; proportional error variance

$ESTIMATION METHOD=1 INTERACTION MAXEVAL=9999 PRINT=5 NOABORT
$COVARIANCE

$TABLE ID TIME AMT DV IPRED IRES IWRES CLCR KA CL V NOPRINT ONEHEADER FILE=metformin_tab.csv

```


## **R Code**

```r

library(mrgsolve)
library(dplyr)
library(ggplot2)

metformin_pk <- '
$PROB
- Metformin PK: one-compartment model with first-order absorption
- Reference: Hong Y, Rohatagi S, Habtemariam B, Walker JR, Schwartz SL, Mager DE. Population exposure-response modeling of metformin in patients with type 2 diabetes mellitus. J Clin Pharmacol. 2008;48(6):696-707. doi:10.1177/0091270008316884

$PARAM @annotated
KA        : 2.15      : 1/h       
CL        : 79.1      : L/h      
V         : 643       : L          
POW       : 0.822     : -- (Power coefficient of CLCR)
CLCR      : 100       : mL/min    
REF_CLCR  : 100       : mL/min     

$CMT @annotated
GUT   : Dosing/absorption compartment (mg)
CENT  : Central compartment (mg)

$OMEGA @labels ETA_KA ETA_CL ETA_V 
0.29 
0.05 
0.17

$SIGMA @labels EPS_ADD EPS_PROP
209
6.12

$MAIN
double KAi    = KA * exp(ETA_KA);
double CLi    = CL * pow(CLCR/REF_CLCR, POW) * exp(ETA_CL);
double Vi     = V  * exp(ETA_V);
double CP_ngmL  = 1000.0*CENT/Vi; 

$ODE
dxdt_GUT  = -KAi*GUT;
dxdt_CENT =  KAi*GUT - (CLi/Vi)*CENT;

$TABLE
capture IPRED = CP_ngmL;
capture DV    = CP_ngmL * (1 + EPS(2)) + EPS(1);        

$CAPTURE 
KAi CLi Vi CLCR REF_CLCR CP_ngmL 
'
mod <- mcode("metformin_pk", metformin_pk)
```

## **Model Scope**

This model only describes the PK portion of the original publication. The PK/PD part is attached below.

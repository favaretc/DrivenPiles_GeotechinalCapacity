# DrivenPiles_GeotechinalCapacity
ASD and LRFD AASHTO Design Procedures to derive geotechnical capacity of driven piles in compression and uplift.

## Applicability:
This code is applicable to:
- Driven Piles
- AASHTO LRFD Procedure
- AASHTO ASD Procedure

## Input:
1. All input are imported/calculated for depths ranging from 0 ft to 120 ft, every 0.25 ft.
### Text Files to Import:
2. Import selected columns from *Effective Stress.xls* into txt files:
	a. SoilUnits.txt [column K] 
	b. Stresses.txt [columns M-N-O]
### Command Line Arguments
 - **pile-diameter** is a float in feet (default : 2 feet)
3. In DrivenPileCapacity_main.py, specify the following:
	a. Pile Diameter [ft]
	b. Pile Shape [circular or square]
	c. LRFD Resistance Factors in Compression (bearing and friction), and Uplift (friction)
4. In DrivenPileCapacity.py, specify the following:
	a. Friction Angle in degrees for all the soil units
	b. Undrained Shear Strength in psf for all the soil units
	c. End Bearing Coefficient (Nq) for all the friction angles [AASHTO LRFD Fig. 10.7.3.8.6f-8]
	d. Coefficient (alpha_t) for all the friction angles [AASHTO LRFD Fig. 10.7.3.8.6f-7]
	e. Limiting Unit Tip Resistance (q_L) for all the soil units [AASHTO LRFD Fig. 10.7.3.8.6f-9]
	f. Correction Factor (C_f) for coefficient of lateral earth pressure for cohesionless friction angles [AASHTO LRFD Fig. 10.7.3.8.6f-5]

### Command Line Arguments
 - **pile-diameter** is a float in feet (default : 2 feet)

#### Example of how to run:
```
python whatever.py --pile-diameter 2 --
```

INPUT:


OUTPUT:
	1. All results are calculated/exported for depths ranging from 0 ft to 120 ft, every 0.25 ft
	2. Unit Tip Resistance vs depth [psf]
	3. Unit Side Resistance vs depth [psf]
	4. Cumulative Side Resistance vs depth [lb]
	5. Tip Resistance vs depth [lb]
	6. Factored Compressive Resistance [kips]: txt + plot
	7. Factored Uplift Resistance [kips]:  txt + plot
	8. Plots
Txt Files

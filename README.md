# DrivenPiles_GeotechinalCapacity
ASD and LRFD AASHTO Design Procedures to derive geotechnical capacity of driven piles in compression and uplift.

## Applicability
This code is applicable to:
- Driven Piles
- AASHTO LRFD Procedure
- AASHTO ASD Procedure

## Input
All input are imported/calculated for depths ranging from 0 ft to 120 ft, every 0.25 ft.

### Text Files to Import
Import selected columns from *Effective Stress.xls* into txt files:
1. SoilUnits.txt [column K] 
2. Stresses.txt [columns M-N-O]
	
Note: if *Effective Stress.xls* is not available, import soil units at every 0.25 ft of depth in *SoilUnits.txt*, and total stresses, pore water pressure, and effective stresses at every 0.25 ft of depth in *Stresses.txt*.

### Csv Files to Edit
Edit the following csv files with location soil properties:
- **soil_properties.csv**:
    - 1st Column: Soil Unit; 
    - 2nd Column: Soil Type (options: Cohesive or Cohesionless) for each Soil Unit;
    - 3rd Column: Friction Angle (degrees) for each Soil Unit; 
    - 4th Column: Undrained Shear Stregth (psf) for each Soil Unit; if Soil Unit is classified as cohesionless, Undrained Shear         	Strength is '-'.
    
- **bearing_coefficients.csv**:
    - 1st Column: Friction Angle (degrees);
    - 2nd Column: End Bearing Coefficient (Nq) for all the friction angles in Column 1 [see AASHTO LRFD Fig. 10.7.3.8.6f-8]; 
    - 3rd Column: Coefficient (alpha_t) for all the friction angles in Column 1 [see AASHTO LRFD Fig. 10.7.3.8.6f-7]
    - 4th Column: Correction Factor (C_f) for coefficient of lateral earth pressure for cohesionless friction angles [AASHTO LRFD Fig.         10.7.3.8.6f-5].
    
- **limiting_unit_tip_resistance.csv**:
    - 1st Column: Soil Unit; 
    - 2nd Column: Limiting Unit Tip Resistance (q_L) for all the soil units [see AASHTO LRFD Fig. 10.7.3.8.6f-9]; if Soil Unit is             classified as cohesive, q_L is '-'.  

### Command Line Arguments
 - **pile-diameter** is a float representing pile diameter in feet (default : 2 feet)
 - **pile_shape** is a string representing pile shape (default: 'circular'; options: 'circular' or 'square')
 - **design** is a string representing type of AASHTO design (default: 'LRFD'; options: 'LRFD' or 'ASD')
 - **LRFD_bearing_clay** is a float representing LRFD Bearing Resistance Factor for Cohesive Soils (default: 0.65)
 - **LRFD_bearing_sand** is a float representing LRFD Bearing Resistance Factor for Cohesionless Soils (default: 0.65)
 - **LRFD_uplift_clay** is a float representing LRFD Uplift Resistance Factor for Cohesive Soils (default: 0.5)
 - **LRFD_uplift_sand** is a float representing LRFD Uplift Resistance Factor for Cohesionless Soils (default: 0.5)
 - **ASDcompression** is a float representing ASD Factor of Safety in Compression (default: 2)
 - **ASDuplift** is a float representing ASD Factor of Safety in Uplift (default: 2)
	
## Output:
1. All results are calculated/exported for depths ranging from 0 ft to 120 ft, every 0.25 ft
2. Unit Tip Resistance vs depth [psf]
3. Unit Side Resistance vs depth [psf]
4. Cumulative Side Resistance vs depth [lb]
5. Tip Resistance vs depth [lb]
6. Factored Compressive Resistance [kips]: txt + plot
7. Factored Uplift Resistance [kips]:  txt + plot
8. Plots

#### Example of how to run:
```
python whatever.py --pile-diameter 2 --
```



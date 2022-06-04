#center ferricyanide in middle of 3.0 box
gmx editconf -f tip4_flex.gro -center 1.5 1.5 1.5 -box 3.0 -o flex_water.gro

#solvate, original OPC paper added 804 waters in 30A box
gmx insert-molecules -f ferri.gro -ci tip4_flex.gro -nmol 804 -try 100 -o flex_water.gro


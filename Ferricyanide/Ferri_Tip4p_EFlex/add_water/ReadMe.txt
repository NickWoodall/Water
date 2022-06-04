#center ferricyanide in middle of 3.0 box
gmx editconf -f ../ff/Ferricyanide_coord.gro -center 1.5 1.5 1.5 -box 3.0 -o ferri.gro

#solvate, original OPC paper added 804 waters in 30A box
gmx insert-molecules -f ferri.gro -ci tip4_flex.gro -nmol 795 -try 100 -o ferri_water.gro


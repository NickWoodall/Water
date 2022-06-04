#center ferricyanide in middle of 3.0 box
gmx editconf -f ../ff/Ferricyanide_coord.gro -center 3.0 3.0 3.0 -box 6.0 -o ferri.gro

#solvate, original OPC paper added 804 waters in 30A box
#added -16 to make room for ferri earlier
#so 804*8-16=6416 (length to volume increase)   aka (6^3/3^3) = 8  
gmx insert-molecules -f ferri.gro -ci opc.gro -nmol 6416 -try 100 -o ferri_water.gro

gmx genion -s ferri_genion.tpr -o ferri_K_ions.gro -p ferricyanide_opc.top -pname K -np 3
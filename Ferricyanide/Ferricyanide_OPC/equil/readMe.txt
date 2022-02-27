#supposed to be 20ps
gmx grompp -f equilibrate_ferri.mdp -c em_ferri.gro -p ferricyanide_opc_ar.top -o equil.tpr

gmx mdrun -v -deffnm equil


trjconv -f equil.xtc -s equil.tpr -n index.ndx -pbc mol -ur compact -center

#choosing FeC for centering
#choosing System for output
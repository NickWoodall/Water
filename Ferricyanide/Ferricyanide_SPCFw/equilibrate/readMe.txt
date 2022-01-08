#supposed to be 1ns
gmx grompp -f equilibrate_ferri.mdp -c em_ferri.gro -p ferricyanide_spcfw.top -o equil.tpr

gmx mdrun -v -deffnm equil
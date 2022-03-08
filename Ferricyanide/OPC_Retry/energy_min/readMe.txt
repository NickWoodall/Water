#generate .tpr file to start run, integrator set to equilibration style in .mdp


gmx grompp -f energyMin_ferri.mdp -c ferri_K_ions.gro -p ferricyanide_op_ar.top -o em_ferri.tpr

#the "em_ferri" specifies all input( .tpr) and output files

gmx mdrun -v -deffnm em_ferri
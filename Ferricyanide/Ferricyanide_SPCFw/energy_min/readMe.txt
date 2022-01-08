#generate .tpr file to start run, integrator set to equilibration style in .mdp


gmx grompp -f equilibrate_ferri.mdp -c ferri_K_ions.gro -p ferricyanide_spcfw.top -o em_ferri.tpr

#the "equil" specifies all input( .tpr) and output files

gmx mdrun -v -deffnm em_ferri
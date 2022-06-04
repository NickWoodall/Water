#generate .tpr file to start run, integrator set to equilibration style in .mdp


gmx grompp -f energyMin.mdp -c flex_box_3.gro -p flex.top -o em.tpr

#the "em_ferri" specifies all input( .tpr) and output files

gmx mdrun -v -deffnm em

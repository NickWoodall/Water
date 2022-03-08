#set for 10ns equilibration, since step is 10greater than original paper and they did 1ns
gmx grompp -f equilibrate_ferri.mdp -c em_ferri.gro -p ferricyanide_opc_ar.top -o equil.tpr

gmx mdrun -v -deffnm equil


gmx trjconv -f equil.xtc -s equil.tpr -pbc mol -ur compact -center

#choosing FeC for centering
#choosing System for output


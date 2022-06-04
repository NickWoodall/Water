#set for 10ns equilibration, since step is 10greater than original paper and they did 1ns
gmx grompp -f equilibrate_ferri.mdp -c em_ferri.gro -p ferricyanide_flex.top -o equil.tpr

gmx mdrun -v -deffnm equil


trjconv -f equil.xtc -s equil.tpr -pbc mol -ur compact -center

#choosing FeC for centering
#choosing System for output


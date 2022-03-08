#set for 100ns run
gmx grompp -f mdrun_20ns_ferri.mdp -c equil.gro -p ferricyanide_opc_ar.top -o md20ns_Ferri

gmx mdrun -v -deffnm md100ns_Ferri


gmx trjconv -f md20ns_Ferri.xtc -s md20ns_Ferri.tpr -pbc mol -ur compact -center

#choosing FeC for centering
#choosing System for output


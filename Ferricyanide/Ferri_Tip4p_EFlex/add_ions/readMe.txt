#first we generate a .tpr file (binary md running file) to pass to genion, grompp like to create
# a new mdpout.mdp file will full options denoted

gmx grompp -f md_ferricyanide.mdp -c ferri_water.gro -p ferricyanide_flex.top -o ferri_genion.tpr -maxwarn 3

gmx genion -s ferri_genion.tpr -o ferri_K_ions.gro -p ferricyanide_flex.top -pname K -np 3
#Select group 4, SOL to replace with K ions. 



gmx grompp -f md_ferricyanide.mdp -c ferri_water_785.gro -p ferricyanide_opc_785.top -o ferri_genion_785.tpr -maxwarn 3

gmx genion -s ferri_genion_785.tpr -o ferri_K_ions_785.gro -p ferricyanide_opc_785.top -pname K -np 3
#Select group 4, SOL to replace with K ions. 
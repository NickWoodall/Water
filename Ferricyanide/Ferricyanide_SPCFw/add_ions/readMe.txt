#first we generate a .tpr file (binary md running file) to pass to genion, grompp like to create
# a new mdpout.mdp file will full options denoted

gmx grompp -f md_ferricyanide.mdp -c ferri_water.gro -p ferricyanide_spcfw.top -o ferri_genion.tpr -maxwarn 3

gmx genion -s ferri_genion.tpr -o ../equilibrate/ferri_K_ions.gro -p ferricyanide_spcfw.top -pname K -np 3
#Select group 4, SOL to replace with K ions. 
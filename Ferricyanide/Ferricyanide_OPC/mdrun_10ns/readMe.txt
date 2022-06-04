#set for 10ns run
gmx grompp -f mdrun_10ns_ferri.mdp -c equil.gro -p ferricyanide_opc_ar.top -o md10ns_Ferri

gmx mdrun -v -deffnm md10ns_Ferri


gmx trjconv -f md10ns_Ferri.xtc -s md100ns_Ferri.tpr -pbc mol -ur compact -center

#choosing FeC for centering
#choosing System for output



#auto correlation 

#add certain atomts to index file

gmx make_ndx -f equil.gro

#in the input, to add OW1
a OW1
a FeC

gmx rdf -n index.ndx -o RDF_OW_FeC -f md10ns_Ferri.xtc -s md10ns_Ferri.tpr 
choose 11/12 for FeC Oxy

gracebat [.xvg file]
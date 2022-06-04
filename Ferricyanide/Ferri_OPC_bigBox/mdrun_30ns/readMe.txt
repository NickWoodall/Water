#set for 10ns run
gmx grompp -f mdrun_30ns_ferri.mdp -c equil.gro -p ferricyanide_opc_ar.top -o md30ns_Ferri

gmx mdrun -v -deffnm md30ns_Ferri


gmx trjconv -f md30ns_Ferri.xtc -s md30ns_Ferri.tpr -pbc mol -ur compact -center

#choosing FeC for centering
#choosing System for output



#auto correlation 

#add certain atomts to index file

gmx make_ndx -f equil.gro

#in the input, to add OW1
a OW
a Fe1

gmx rdf -n index.ndx -o RDF_OW_FeC_20_30 -f md30ns_Ferri.xtc -s md30ns_Ferri.tpr -b 20000
choose 11/12 for FeC Oxy

gracebat [.xvg file]
#set for 10ns run
gmx grompp -f mdrun_120ns_ferri.mdp -c equil.gro -p ferricyanide_opc_ar.top -o md120ns_Ferri

gmx mdrun -v -deffnm md120ns_Ferri

gmx trjconv -f md120ns_Ferri.xtc -s md120ns_Ferri.tpr -pbc mol -ur compact -center

#choosing FeC for centering
#choosing System for output



#auto correlation 

#add certain atomts to index file

gmx make_ndx -f equil.gro

#in the input, to add OW1
a OW
a Fe1

gmx rdf -n index.ndx -o RDF_OW_FeC -f md120ns_Ferri.xtc -s md120ns_Ferri.tpr -b 110000
choose 11/12 for FeC Oxy

gracebat [.xvg file]


Extend RUN???

extend with tpr and checkpoint

gmx convert-tpr -s md60ns_Ferri.tpr -extend 60000 -o md_extend_to_120ns.tpr
gmx mdrun -s md_extend_to_120ns.tpr -cpi md60ns_Ferri_prev.cpt
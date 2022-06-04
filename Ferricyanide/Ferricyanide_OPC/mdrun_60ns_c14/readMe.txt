#set for 10ns run
gmx grompp -f mdrun_60ns_ferri.mdp -c equil.gro -p ferricyanide_opc_ar.top -o md60ns_Ferri

gmx mdrun -v -deffnm md60ns_Ferri

gmx trjconv -f md60ns_Ferri.xtc -s md60ns_Ferri.tpr -pbc mol -ur compact -center

#choosing FeC for centering
#choosing System for output



#auto correlation 

#add certain atomts to index file

gmx make_ndx -f equil.gro

#in the input, to add OW1
a OW1
a FeC

gmx rdf -n index.ndx -o RDF_OW_FeC -f md60ns_Ferri.xtc -s md60ns_Ferri.tpr -b 40000 
choose 11/12 for FeC Oxy

gracebat [.xvg file]


Extend RUN
WHY NO WORK?

extend with tpr and checkpoint

gmx convert-tpr -s md60ns_Ferri.tpr -extend 60000 -o md_extend_to_120ns.tpr
gmx mdrun -s md_extend_to_120ns.tpr -cpi md60ns_Ferri_prev.cpt
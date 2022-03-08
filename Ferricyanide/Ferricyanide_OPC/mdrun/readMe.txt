#set for 10ns run
gmx grompp -f mdrun_10ns_ferri.mdp -c equil.gro -p ferricyanide_opc_ar.top -o md10ns_Ferri

gmx mdrun -v -deffnm md10ns_Ferri


gmx trjconv -f md10ns_Ferri.xtc -s md100ns_Ferri.tpr -pbc mol -ur compact -center

#choosing FeC for centering
#choosing System for output



#auto correlation function

#add certain atomts to index file

gmx make_ndx -f equil.gro

#in the input, to add OW1
a OW1
a FeC

gmx rdf -n index.ndx -o RDF_OW_FeC -f md10ns_Ferri.xtc -s md10ns_Ferri.tpr 

#choose 11/12 to get Fe - O atom pair

#I downloaded grace which can do the .xvg file conversion to .ps
#.xvg is some sort of comma delimited file with liek ~26 lines of comments at the beginning. I tried in excel but something wasn't right, but theoretically
#can do [sudo apt-get install grace] 

#makes a .ps (post-script file) pain to view
gracebat RDF_OW_FeC

which is vieweable
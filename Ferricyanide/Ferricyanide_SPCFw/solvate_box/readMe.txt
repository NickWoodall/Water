Command to run:

gmx solvate -cp box_Ferricyanide_coord.gro -cs /usr/local/share/gromacs/top/spc216.gro -p ferricyanide_spcfw.top -box 3.0 3.0 3.0 -o ../add_ions/ferri_water.gro


#box size is also on the last line of the ferricyanide_coord.gro file
#.top file is re-written to add waters, old is re-saved with #
#this function takes the box of 3 point charge waters in spc216.gro and placeres the ferricyanide in the middel
#will have to remake for non-standard 3 point charge waters
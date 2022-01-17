Command to run:

#center ferricyanide in middle of 3.0 box
gmx editconf -f box_Ferricyanide_coord.gro -center 1.5 1.5 1.5 -box 3.0 -o ferri.gro

gmx solvate -cp ferri.gro -p ferricyanide_spcfw.top -o ferri_water.gro -cs /usr/local/gromacs/share/gromacs/top/spc216.gro
#box size is also on the last line of the ferricyanide_coord.gro file
#.top file is re-written to add waters, old is re-saved with #
#this function takes the box of 3 point charge waters in spc216.gro and placeres the ferricyanide in the middel
#will have to remake for non-standard 3 point charge waters
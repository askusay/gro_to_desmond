# gro_to_desmond
A basic converter from the gromacs topology format to desmond CMS

### Installation:
Install modified parmed from: https://github.com/askusay/ParmEd

*This contains comments to lines 1687-1689 of topologyobjects.py to supress errors from reading gromacs top files (I believe the error comes from virtual sites in the GROMOS 54A7 forcefield*
```
        # COMMENTED THIS OUT TO SUPRESS GROMOS 54A7 WARNINGS ABOUT VIRTUAL SITES
        #if isinstance(atom1, ExtraPoint) and isinstance(atom2, ExtraPoint):
        #    raise MoleculeError('Cannot bond two virtual sites/extra points together')
```
### Instructions
The code is in the Jupyter notebook
1) Load the topology file with coordinates using: `top = gromacs.GromacsTopologyFile('exmaple.top', parametrize=False, xyz='example.gro')`
  - xyz accepts other coord files like pdb 
2) Covert using: `write_cms(top, filename='exmaple.cms', traj_file='exmaple.xtc')`
  - Desmond .dtr trajectories also work for traj_file

### Results 
Enables doing some analyses in Maestro Desmond like direct/water mediated hydrogen bond interaction diagrams, see attached pdf 

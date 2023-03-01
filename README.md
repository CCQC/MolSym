<p align="center">
  <img src="molsym.png" width="400" alt=""/>
</p>

# MolSym
A python package for handling molecular symmetry!
<table align="center">
  <tr>
    <th>Documentation</th>
    <th>Build Status</th>
    <th>License</th>
  </tr>
  <tr>
    <td align="center">
      <a href=https://FermiQC.github.io/Fermi.jl/dev>
      <img src=https://img.shields.io/badge/docs-dev-blue.svg>
      </a> 
    </td>
    <td align="center">
      <a href=https://github.com/FermiQC/Fermi.jl/actions/workflows/CI.yml>
      <img src=https://github.com/FermiQC/Fermi.jl/actions/workflows/CI.yml/badge.svg>
      </a> 
      <a href=https://codecov.io/gh/FermiQC/Fermi.jl>
      <img src=https://codecov.io/gh/FermiQC/Fermi.jl/branch/master/graph/badge.svg?token=EWRG6Q7FK9>
      </a> 
    </td>
    <td align="center">
      <a href=https://github.com/FermiQC/Fermi.jl/blob/master/LICENSE>
      <img src=https://img.shields.io/badge/License-MIT-blue.svg>
      </a>
    </td>
  </tr>
</table>

## Capabilities
-Point group detection
-Symmetry element generation
-Character table generation
-SALC generation for atomic basis functions, internal coordinates, and cartesian coordinates
Currently, we have implementations of:

| Method    | Conv. | DF |
|-----------|-------|----|
| RHF       |  Y    |  Y |
| RMP2      |  Y    |  Y |
| RCCSD     |  Y    |  Y |
| RCCSD(T)  |  Y    |  Y |


## Contribute
PR's, issues, and suggestions are very welcome! You might consider reaching out before starting
work so that we can avoid duplication of efforts.

## Install
Install Fermi by running,
```
pkg> add Fermi
```
If you would like the latest updates, use instead
```
pkg> add Fermi
```
Everything should work automatically, the most flagile part is building the integral library [libcint](https://github.com/sunqm/libcint). The file [`deps/build.jl`](https://github.com/gustavojra/Fermi.jl/blob/master/deps/build.jl) contains simple commands to clone and build this library, you might need to modify it to better suit your system. If you do, rerun the build step using `pkg> build Fermi`. Please reach out 
if you encounter any problem.

## Running single point energies
A minimal example of a computation is provided here. For more info check the documentation.

First, define a molecule
```
@molecule {
  O        1.2091536548      1.7664118189     -0.0171613972
  H        2.1984800075      1.7977100627      0.0121161719
  H        0.9197881882      2.4580185570      0.6297938830
}
```
Choose a basis set
```
@set basis sto-3g
```
Finally run a computation
```
@energy ccsd;
```

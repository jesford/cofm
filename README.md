## Concentration-Mass relations

This python code calculates halo concentration, given halo mass and redshift. 

I plan to add more c(M) relations from the literature (and you are more than welcome to contribute your favorite relation), but for now, there are two c(M) relations included as functions in this module:

- **c_Prada(z,m)**: which is based on [Prada et al. (2012)](http://arxiv.org/abs/1104.5130)

- **c_DuttonMaccio(z,m)**: from [Dutton & Maccio (2014)](http://arxiv.org/abs/1402.7073)


#### How to use this code

Both functions require, at minimum, a single redshift and a mass, for which to calculate halo concentration. Mass is defined as M200 (the total mass interior to a sphere within which the average density is 200 times the critical energy density of the universe) and must be given in units of solar mass. 

Lists or numpy arrays of redshift and/or mass can also be passed to the function. *If an array-like quantity is passed* for either of the input parameters, than the other parameter must be:
1. an array-like variable of the same length, **OR**
2. a single floating point value (or array of length one). 

In the first case, each element of redshift is matched up with the corresponding element of mass, returning an array of concentration values that has the same length. In the second case, the single float value will be applied to each element of the array, returning an array of concentration values of the same length as the multi-element array given as input. Inputing 2 multi-element arrays of different lengths will raise an error.


#### Examples

from cofm import c_Prada,c_DuttonMaccio

print c_Prada(0.1,3e14)

print c_DuttonMaccio(0.1,3e14)

z = [0.1,0.3,0.5,0.7]

m = 1e14

print c_Prada(z,m)

print c_DuttonMaccio(z,m)

m = [1e12,1e13,1e14,1e15]

print c_Prada(z,m)

print c_DuttonMaccio(z,m)


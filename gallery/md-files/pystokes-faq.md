![Image](https://raw.githubusercontent.com/rajeshrinet/pystokes-misc/master/gallery/figs/thisPyIm.png)

## Phoresis and Stokesian hydrodynamics

[Phoretic interactions](#phoretic-interactions) | [Hydrodynamic interactions](#hydrodynamic-interactions) | [Installation](#installation) | [Reading](#reading) 


PyStokes is a Python library for studying phoretic and hydrodynamic interactions between spherical particles. In particular, the library has been specifically designed for studying these interactions in suspensions of active particles. Such particles are distinguished by their ability to produce flow, and thus motion, in the absence of external forces or torques. Active particles are endowed with a mechanism to produce hydrodynamic flow in a thin interfacial layer, which may be due to the motion of cilia, as in microorganisms (Brennen & Winet, 1977) or osmotic flows of various kinds in response to spontaneously generated gradients of phoretic fields (Ebbens & Howse, 2010). The latter, often called autophoresis as we describe in more detail below. 



## Phoretic interactions

Phoresis means motion of colloidal particles in response to interfacial forces.  Quoting (JL Anderson, Ann Rev Fluid Mech (1989))

> Phoretic transport is defined as the movement of colloidal particles by a field that interacts with the surface of each particle

* **What are examples phoresis?**  Examples of phoresis (phoretic field) are electrophoresis (electric field), diffusiophoresis (concentration of chemical field), thermophoresis (temperature field) etc.  The phoretic motion of the colloid in this case is due to the externally imposed electric field. The phoretic transport results from an electrophoretic slip velocity on the surface of the particles as we now describe.

* **Electrophoresis: how does a neutral object (charged particle with negative counter-ions) propel under the effect of electric field?** Consider a particle with a charge q in a non-conducting fluid. Once an electric field E is applied, the colloid moves due to the body force qE acting on it. The motion also creates flow v, which decays as v ~1/r, where r is the distance from the colloid. On the other hand, if the fluid is electrolytic, then the flow decays as v ~ 1/r^3. Why?<br/>As described in the figure below, a charged particle in an electrolytic fluid is effectively neutral due to the cloud of counter-ions around it. Thus, there is no net body force and the colloid should not move! It does due to the fact that the counter-ions are mobile, which leads to a `slip` velocity of the surface of the particle. Solving the Stokes equation with this slip boundary condition gives v ~ 1/r^3.![Image](https://raw.githubusercontent.com/rajeshrinet/pystokes-misc/master/gallery/figs/electrophoresis.jpg)

* **What is self-diffusiophoretic motion of active particles**?  The autophoretic particles self-propel due to a non-equilibrium process, such as chemical reactions on their surface. The phrase auto-phoresis is used interchangeably with self-phoresis.    Active particles are distinguished by the fact that the slip velocity does not result from an externally imposed field, but is spontaneously generated  in response to gradients of phoretic fields. A particle is “active” if it creates the phoretic field itself (for example, by a built-in chemical asymmetry on its surface), and the resulting
phenomena is called self-phoresis

![Image](https://raw.githubusercontent.com/rajeshrinet/pystokes-misc/master/gallery/figs/self-diffusiophoresis.jpg)

* **What are phoretic interactions?** The phoretic field on the surface of the particles can be modified by the proximity of other particles. Briefly, the active slip on the surface of the particles is function of chemical fluxes on the surface of all the particles and distances between them. A complete theory of these interactions is available in J. Chem. Phys. 151, 044901 (2019). 

## Hydrodynamic interactions

* **What equation does PyStokes solve**?  PyStokes allows to compute phoretic and/or hydrodynamic interactions in active colloidal suspensions, when these interactions can be described by the solutions of, respectively, the Laplace and Stokes equations. The PyStokes library can also compute hydrodynamically correlated Brownian motion. Thus it allows the study of the interplay between passive, active, and Brownian contributions to motion.

* **Does PyStokes resolve fluid degrees of freedom?**  PyStokes allows freedom from grids, both in the bulk of the fluid and on the particle boundaries. PyStokes uses analytical solutions for the boundary integral equation of Stokes flow which reduces the dimensionality of the problem from a three-dimensional one in volume $V$ to a two-dimensional one on surface $S$ of the particles.




## Installation

You can take PyStokes for a spin **without installation**: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/rajeshrinet/pystokes/master?filepath=binder). Please be patient while [Binder](https://mybinder.org/v2/gh/rajeshrinet/pystokes/master?filepath=binder) loads. 

### Via [Anaconda](https://docs.conda.io/projects/continuumio-conda/en/latest/user-guide/install/index.html)

Install PyStokes and its dependencies in an [environment](https://github.com/rajeshrinet/pystokes/blob/master/environment.yml) named pystokes:

```bash
>> git clone https://github.com/rajeshrinet/pystokes.git
>> cd pystokes
>> make env
>> conda activate pystokes
>> make
```

### Via pip

Install the latest [PyPI](https://pypi.org/project/pystokes) version

```bash
>> pip install pystokes
```

### From a checkout of this repo

Install PyStokes and required dependencies using

```bash
>> git clone https://github.com/rajeshrinet/pystokes.git
>> cd pystokes
>> pip install -r requirements.txt
>> python setup.py install
```

### Testing
Short test of installation and running

```bash
>> cd tests
>> python shortTests.py
```

Long test of example notebooks 

```bash
>> cd tests
>> python notebookTests.py
```

## Reading

* [Hydrodynamic and phoretic interactions of active particles in Python](https://arxiv.org/abs/1910.00909), Rajesh Singh and R. Adhikari, arXiv:1910.00909, 2019. *(Please cite this paper if you use PyStokes in your research)*.

* [Competing phoretic and hydrodynamic interactions in autophoretic colloidal suspensions](https://aip.scitation.org/doi/full/10.1063/1.5090179), Rajesh Singh, R. Adhikari, and M. E. Cates, **The Journal of Chemical Physics** 151, 044901 (2019)

* [Generalized Stokes laws for active colloids and their applications](https://iopscience.iop.org/article/10.1088/2399-6528/aaab0d), Rajesh Singh and R. Adhikari, **Journal of Physics Communications**, 2, 025025 (2018)


* [Flow-induced phase separation of active particles is controlled by boundary conditions](https://www.pnas.org/content/115/21/5403), Shashi Thutupalli, Delphine Geyer, Rajesh Singh, R. Adhikari, and Howard A. Stone, **Proceedings of the National Academy of Sciences**, 115, 5403 (2018)  

* [Universal hydrodynamic mechanisms for crystallization in active colloidal suspensions](https://doi.org/10.1103/PhysRevLett.117.228002), Rajesh Singh and R. Adhikari,  **Physical Review Letters**, 117, 228002 (2016)


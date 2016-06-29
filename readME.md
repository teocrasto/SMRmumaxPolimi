Mumax3 simulation code for a reconfigurable logic gate for domain wall propagation
===

There are two main files in this repository: __ANDgate.mx3__ and __ORgate.mx3__
They contain the code used to run the simulation with [mumax3](http://mumax.github.io).

All the device is inside a magnetic field __Hext__ directed from left to right.

The logic function of the gate can be modified by controlling a local __Hbias__ field antiparallel to the external field and modelleld in the code as a magnetic field applied only in a specific region, the driver (i.e. the D (or MID) region defined in `/mask`).

The masks used for telling mumax the geometry of the problem and the geometry of the different regions considered are stored in the subfolder `/mask`. In this folder there are either `.png` black/white images either `.pdf` files. They were both generated from a CAD drawing software.

The code simply runs a simulation with real material parameters (permalloy) and saves, for each timestep specified in the `save` function, the magnetization along the device and in the central region. This is useful to track down the domain wall motion and derive its speed. The files are saved either in a table (raw text file, `.txt`) or in the container format `.ovf`.
`.ovf` files can be easily converted in images or other handy data format with the built-in utility `mumax-convert`.


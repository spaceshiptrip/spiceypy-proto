# SPICE Ephemeris Search

The goal of this prototype is to return ephemeris data for item requested.

Kernels will have to be supplied.

This is a test to try and get query data from SPICE based on a python app.

### Set up Python Development Environment using virtualenv
In a development environment, make sure you have the following:
```
python3
pip3
virtualenv
```
Steps:

1. To install virtualenv
   ```
   pip3 install --user virtualenv
   ```
1. Set up virtualenv venv
   ```
   python3 -m virtualenv venv
   ```
1. Go into the virtualenv (defaults to bash, use appropriate source file for other shells):
   ```
   source venv/bin/activate
   ```
You can now program in python installing requirements specific to your program without affecting the entire system.


### Install `requirements.txt`
```
pip3 install -r requirements.txt
```


## SPICE Examples

1. tkvrsn.py
1. plot-cassini.py

#### tkvrsn.py
Python program that prints the version number of spice

#### plot-cassini.py
A little more complex examples that loads kernels and uses matplot to plot out CASSINI trajectories.

For the cassMetaK.txt file to work, it expects kernels to be in a directory structure:
```
... <base directory>
  |
  |_ kernels
       |
       |_ cassini
```

Need to download the kernels from NAIF and put them in the `kernels/cassini` directory:
https://naif.jpl.nasa.gov/pub/naif/generic_kernels/lsk/a_old_versions/naif0009.tls
https://naif.jpl.nasa.gov/pub/naif/CASSINI/kernels/sclk/cas00084.tsc
https://naif.jpl.nasa.gov/pub/naif/CASSINI/kernels/pck/cpck05Mar2004.tpc
https://naif.jpl.nasa.gov/pub/naif/CASSINI/kernels/fk/release.11/cas_v37.tf
https://naif.jpl.nasa.gov/pub/naif/CASSINI/kernels/ck/04135_04171pc_psiv2.bc
https://naif.jpl.nasa.gov/pub/naif/CASSINI/kernels/spk/030201AP_SK_SM546_T45.bsp
https://naif.jpl.nasa.gov/pub/naif/CASSINI/kernels/ik/release.11/cas_iss_v09.ti
https://naif.jpl.nasa.gov/pub/naif/CASSINI/kernels/spk/020514_SE_SAT105.bsp
https://naif.jpl.nasa.gov/pub/naif/CASSINI/kernels/spk/981005_PLTEPH-DE405S.bsp

**Kernels are not included in github due to size limitations Git LFS latencies**

#### plot-mars.py

```
... <base directory>
  |
  |_ kernels
       |
       |_ mars
```

Need to download the kernels:
https://naif.jpl.nasa.gov/pub/naif/generic_kernels/lsk/naif0012.tls
https://naif.jpl.nasa.gov/pub/naif/generic_kernels/spk/satellites/mar097.bsp
https://naif.jpl.nasa.gov/pub/naif/generic_kernels/spk/satellites/mar097.cmt
https://naif.jpl.nasa.gov/pub/naif/generic_kernels/spk/satellites/mar097.inp
https://naif.jpl.nasa.gov/pub/naif/generic_kernels/spk/planets/de440.bsp
https://naif.jpl.nasa.gov/pub/naif/generic_kernels/spk/planets/de440_tech-comments.txt



## Further Reading
1. de440.bsp versus de441-partX.bsp: 
   (Documentation)[https://naif.jpl.nasa.gov/pub/naif/generic_kernels/spk/planets/de441_tech-comments.txt]
   ```
   The ephemerides DE440 and DE441 are fitted to the same data set, but DE441 assumes no damping between lunar liquid core and solid mantle, which avoids a divergence when integrated backwards in time. Therefore, DE441 is less accurate than DE440 for the current century, but covers a much longer duration of years -13,200 to +17,191, compared to DE440 covering years 1,550 to 2,650.

   ```
   For smaller file footprint, use `de440.bsp`

1. MetaKernels: https://naif.jpl.nasa.gov/pub/naif/toolkit_docs/C/req/kernel.html#Path%20Symbols%20in%20Meta-kernels
1. Cassini Example: https://spiceypy.readthedocs.io/en/main/exampleone.html
1. WebGeocalc: https://wgc.jpl.nasa.gov:8443/webgeocalc/#NewCalculation
   * python binding for webgeocalc restful API: https://github.com/seignovert/python-webgeocalc
   


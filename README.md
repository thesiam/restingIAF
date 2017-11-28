# restingIAF
## General information
Source code for `restingIAF`, an automated resting-state individual alpha frequency (IAF) estimation routine implemented in EEGLAB. 

Repo also contains a manuscript (long and short(er) versions, archived on bioRxiv) outlining rationale for programme development, its performance across simulated and non-simulated EEG datasets, and guidelines for parameter settings.
The [long version](https://github.com/corcorana/restingIAF/blob/master/MS_long.pdf) contains additional details concerning some of the problematic aspects of many common approaches to IAF estimation.
The [short version](https://github.com/corcorana/restingIAF/blob/master/MS_short.pdf) (currently under review) also omits some of the technical details included in the long version.
Most of these details have been collated in an accompanying [appendix](https://github.com/corcorana/restingIAF/blob/master/MS_short_appendix.pdf).

## Simulation analyses
Materials required to replicate the simulation analyses reported in the manuscipt can be found in the [simulations](https://github.com/corcorana/restingIAF/tree/master/simulations) directory.
Run `simsSingle` to replicate the preliminary (single component) analysis; run `simsMulti` for the multiple channels / mixed components analyses.
These scripts include code to reproduce the tables and figures included in the results section of the manuscript.

Simulations depend on the `pinknoise` function (v1.5), which has been included as part of the simulation materials.
Please see the [LICENSE](https://github.com/corcorana/restingIAF/tree/master/simulations/pinknoise_LICENSE.txt) associated with this source code for terms and conditions of its use and distribution.
Updates and more information about the function (along with others for generating red, blue, and violet noise signal) can be accessed from the [MATLAB File Exchange](https://au.mathworks.com/matlabcentral/fileexchange/42919-pink--red--blue-and-violet-noise-generation-with-matlab-implementation).

## Tutorial analysis
A [tutorial](https://github.com/corcorana/restingIAF/tree/master/tutorial) analysis routine (including sample EEG data) is provided to familiarise you with various features of the package.
This script may serve as a useful model for integrating `restingIAF` within your own pipeline, however we strongly recommend that you carefully consider whether the approach implemented in the tutorial is suitable for your analysis plan.

If you experience any difficulties implementing `restingIAF`, please attempt to replicate the analysis detailed in the [tutorial readme](https://github.com/corcorana/restingIAF/tree/master/tutorial/tute_README.md) before contacting us for assistance.

## Development
All functions were developed and tested in MATLAB 2014b/2015a, and may not be fully compatible with other versions of MATLAB. 
The algorithm is dependent on the `Signal Processing Toolbox`.

Software developed in collaboration with Dr. Phillip Alday, Prof. Matthias Schlesewsky, & Prof. Ina Bornkessel-Schlesewsky at the Centre for Cognitive and Systems Neuroscience, University of South Australia.

Constructive criticism, corrections, and potential improvements are most welcome.

E-mail: andrew{dot}corcoran1{at}monash{dot}edu | Twitter: {at}mr_corcorana

## Python implementation
A preliminary implementation in Python for use with [MNE-Python](https://martinos.org/mne/) is available as part of the [`philistine` package](https://gitlab.com/palday/philistine).

## Citation
If this software was useful for your work, please consider citing our methods paper: 

> Corcoran, A.W., Alday, P.M., Schlesewsky, M., & Bornkessel-Schlesewsky, I. (2017). Towards a reliable, automated method of individual alpha frequency (IAF) quantification. bioRxiv. doi: https://doi.org/10.1101/176792

The current release version can also be cited:

> Corcoran, A.W., Alday, P.M., Schlesewsky, M., & Bornkessel-Schlesewsky, I. (2017). restingIAF (version number) [Software]. Retrieved from https://github.com/corcorana/restingIAF. [doi]

Each version release is issued a unique doi from [Zenodo](https://zenodo.org/).

## Current release
`v1.0.2` [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1066004.svg)](https://doi.org/10.5281/zenodo.1066004)

Various updates and minor bug fixes, including:

- SGF parameters must now be specified (i.e. no default setting);
- 'psd' argument removed from call to `pwelch` in `restingIAF`;
- option to implement `pwelch` using an alternative taper to the default Hamming window;
- `meanIAF` reconfigured to cope with >2 sets of intraindividual recordings;
- `plotAvSpec` added to enable plotting of (Q-weighted) averaged channel spectra;
- tutorial updated to include example figures from `plotAvSpec`;
- simulation script separated into single & multi-component analyse scripts;
- tutorial and simulation scripts updated in line with above modifications.

### Previous releases
`v1.0.1` [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.888071.svg)](https://doi.org/10.5281/zenodo.888071)

`v1.0` [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.846797.svg)](https://doi.org/10.5281/zenodo.846797)

`v0.1` [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.268602.svg)](https://doi.org/10.5281/zenodo.268602)

## Licence & Copyright
This software was developed in the hope that it would be of some use to the EEG research community, and is freely available for redistribution and/or modification under the terms of the GNU General Public Licence.
It is distributed WITHOUT WARRANTY; without even the implied warranty of merchantability or fitness for a particular purpose. 
See the [GNU General Public License](https://github.com/corcorana/restingIAF/tree/master/LICENCE.md) for more details.

Copyright (c) 2016-2017 Andrew W. Corcoran.
(Any coding errors or inelegancies are solely his fault.)

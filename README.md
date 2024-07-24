# Matter Power Spectra Release for Fable MPS Study:
**Stirring the cosmic pot: how black hole feedback shapes the matter power spectrum in the \textsc{fable} simulations**
Hyperlink to manuscript studying the MPS in Fable: to be included
Hyperlink to ADS entry: to be included

**Authors:**
Sergio Martin-Alvarez, Vid Iršič, Sophie Koudmani, Martin Bourne, Leah Bigwood, and Debora Sijacki

### Fable simulation:
The Fable simulations are cosmological hydrodynamical simulations using the AREPO code, incorporating updated AGN and supernova feedback models. They accurately reproduce galaxy formation and cluster properties, aligning well with observed scaling relations.

Fable was originally created and presented by Nicholas A. Henden, in:
Henden N. A., Puchwein E., Shen S., Sĳacki D., 2018, MNRAS, 479, 5385
Hyperlink to published journal article presenting Fable: https://academic.oup.com/mnras/article/479/4/5385/5051752
ADS entry: https://ui.adsabs.harvard.edu/abs/2018MNRAS.479.5385H/abstract 

### Contact:
For any questions or issues, please contact Sergio Martin-Alvarez at:
martin-alvarez@stanford.edu

## Description

This repository contains some useful Fable MPS data presented in Martin-Alvarez et al. submitted.

The data files (see data directory) are ASCII files identified with extensions `.dat`, and contain information about the power spectrum of different Fable simulations, each generated with different AGN feedback models. This README file provides an overview of the data files, their format, and how to use the provided Python script to read and plot the data.

## Usage

To access the provided data files using python you can use the 'read_FFT_file' function in the support_io.py file. That file also contains some basic examples of how to access the data and display the raw spectra. It requires either the `pandas` (recommended) or `numpy` library.

## Data Files

Each data file follows the same format and contains four sections: the simulation header, the FFT header, the units header, and the data section. Below is a detailed description of each section.


### Data Files: Sections

1. **Simulation Header**:
    - Contains the simulation parameters.
    - Example:
      ```
      Lbox (cMpc) =  58.909793673384 :> Size of the box in comoving Mpc
      ngrid (cells) =     1024       :> Number of grid cells in each dimension
      aexp =   1.000000000000        :> Expansion scale factor
      h0 =   0.677399992943          :> Reduced hubble constant (H0) in units of 100 km/s/Mpc
      ns =   0.966700017452          :> Spectral index of the initial power spectrum
      sigma8 =   0.815900027752      :> Root mean square fluctuation of the density field on 8 Mpc/h scales
      Omega_l =   0.691100001335     :> Density parameter for dark energy (Λ) in units of the critical density
      Omega_m =   0.308899998665     :> Density parameter for matter (Ωm) in units of the critical density
      Omega_b =   0.048599999398     :> Density parameter for baryons (Ωb) in units of the critical density
      Omega_k =   0.000000000000     :> Density parameter for curvature (Ωk) in units of the critical density
      ```

2. **FFT Header**:
    - Contains details about the FFT calculation.
    - Example:
      ```
      FFTtype =     powerspectrum      :> Type of FFT calculation (powerspectrum in this case)
      ShotNoise =                 0    :> Shot noise correction value (0 indicates no shot-noise correction included here)
      var1 = totalmass_overdens        :> First variable used in the FFT calculation (total mass overdensity)
      var2 =              empty        :> Second variable used in the FFT calculation (empty, not used)
      var3 =              empty        :> Third variable used in the FFT calculation (empty, not used)
      neff1 (count) =     181774039.73 :> Effective number of elements contributing to the first variable
      neff2 (count) =    1073741824.00 :> Effective number of elements contributing to the second variable
      neff3 (count) =    1073741824.00 :> Effective number of elements contributing to the third variable
      ```

3. **Units Header**:
    - Describes the units of the columns in the data section.
    - Example:
      ```
      k (Mpc^-1)        P (Mpc^3) P-NoCorr (Mpc^3)  nmodes (counts)
      ```
    - Quantities description:
      - k        : Wave number (k) in units of Mpc^-1
      - P        : Power spectrum (P) in units of Mpc^3
      - P-NoCorr : Power spectrum without shot noise correction (P-NoCorr) in units of Mpc^3
      - nmodes   : Number of modes contributing to the bin (nmodes)
4. **Data Section**:
    - Contains the actual data, with columns specified in the Units Header.
    - Example:
      ```
      0.10789E+00      0.29477E+04      0.29477E+04                5
      0.15240E+00      0.38977E+04      0.38976E+04                8
      ...
      ```
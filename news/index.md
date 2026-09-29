# Changelog

## wmm 1.1.3

1.  Added `inst/extdata/coefficients/` to store legacy coefficient
    files, though these are included in `.gitignore`.
2.  Added WMM2025 coefficient path to `data-raw/creatingSysData.R`.
3.  Added WMM2025 test values to `inst/extdata/WMMTestValues.csv`.
4.  Recalculated `R/sysdata.rda` to incorporate WMM2025 coefficients.
5.  Removed legacy roxygen syntax in `R/wmm.R`.
6.  In `R/functions_wmm.R`, updated roxygen labels and `wmmVersion`
    [@param](https://github.com/param) descriptions to include
    ‘WMM2025’, where appropriate.
7.  In `R/functions_wmm.R`, included ‘WMM2000’ in `wmmVersion`
    [@param](https://github.com/param) description of
    `.CalculateMagneticField`.
8.  In `R/functions_wmm.R`, updated
    [@examples](https://github.com/examples) for `GetMagneticFieldWMM`
    to use an example from the official WMM2025 test values.
9.  In `R/functions_misc.R`, added date ranges for WMM2025 and WMM2000
    coefficients in `.DeriveVersionInfo`.
10. In `R/functions_misc.R`, included ‘WMM2025’ in `wmmVersion`
    [@param](https://github.com/param) description of
    `.CheckVersionWMM`.
11. In `R/functions_misc.R`, updated URL for ‘Performance Specifications
    WMM’ in `.CheckBlackoutZone`.
12. In `R/functions_coefficients.R`, included ‘WMM2025’ in `wmmVersion`
    [@param](https://github.com/param) description of
    `.CalculateGaussCoef`.
13. Updated documentation in manual.
14. Updated `tests/testthat.R` to work in vscode.
15. Updated `vignettes/` to reference WMM2025, where appropriate.
16. In `DESCRIPTION`:

&nbsp;

1.  updated supported date ranges
2.  included WMM2025 citation
3.  updated versions within `Depends` and `Suggests`

&nbsp;

17. In `README.md`:

&nbsp;

1.  updated supported date ranges
2.  included WMM2025 citation

&nbsp;

18. Updated `renv.lock` to use latest package versions and R 4.3.3.

## wmm 1.1.2

1.  Added HTML vignette.
2.  Added [@noRd](https://github.com/noRd) flag for internal functions.
3.  Added docs/CONTRIBUTING.md
4.  Added codemeta.json file.

## wmm 1.1.1

CRAN release: 2021-09-06

1.  Removed WMM coefficient files and URLs.
2.  Adding note to README re: WMM output as predictions and referenced
    IGRF.

## wmm 1.1.0

CRAN release: 2021-03-17

1.  Updated Gauss coefficients for WMM2020.
2.  Significantly improved numerical stability by using closed-form
    equation for associated Legendre polynomials, instead of recursion.
3.  Improved speed by ~7x by using multidimensional arrays.
4.  Per WMM2020, this version now displays a blackout zone warning when
    the horizontal intensity is below 6000 nT.
5.  In addition to orthogonal magnetic field components,
    `GetMagneticFieldWMM` returns the magnetic field elements *h*, *f*,
    *i*, & *d* as well as their secular variation.

## wmm 1.0.0

CRAN release: 2019-11-22

First release of wmm package. Contains 1 exported function,
`GetMagneticFieldWMM`, which calculates magnetic field.

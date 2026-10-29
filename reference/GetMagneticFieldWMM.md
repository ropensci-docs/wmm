# Calculate Expected Magnetic Field from WMM

Function that takes in geodetic GPS location and annualized time, and
returns the expected magnetic field from WMM.

## Usage

``` r
GetMagneticFieldWMM(lon, lat, height, time, wmmVersion = "derived")

wmm(lon, lat, height, time, wmmVersion = "derived")
```

## Arguments

- lon:

  GPS longitude

- lat:

  GPS latitude, geodetic

- height:

  GPS height in meters above ellipsoid

- time:

  Annualized date time. E.g., 2015-02-01 = (2015 + 32/365) = 2015.088;
  optionally an object (length 1) of class 'POSIXt' or 'Date'

- wmmVersion:

  String representing WMM version to use. Must be consistent with `time`
  and one of the following: 'derived', 'WMM2000', 'WMM2005', 'WMM2010',
  'WMM2015', 'WMM2015v2', 'WMM2020', 'WMM2025'. Default 'derived' value
  will infer the latest WMM version consistent with `time`.

## Value

`list` of calculated main field and secular variation vector components
in nT and nT/yr, resp. The magnetic element intensities (i.e.,
horizontal and total intensities, h & f) are in nT and the magnetic
element angles (i.e., inclination and declination, i & d) are in
degrees, with their secular variation in nT/yr and deg/yr, resp.: `x`,
`y`, `z`, `xDot`, `yDot`, `zDot`, `h`, `f`, `i`, `d`, `hDot`, `fDot`,
`iDot`, `dDot`

## Examples

``` r
GetMagneticFieldWMM(
   lon = 240,
   lat = -80,
   height = 0,
   time = 2025,
   wmmVersion = 'WMM2025'
)
#> $x
#> [1] 6117.548
#> 
#> $y
#> [1] 15751.91
#> 
#> $z
#> [1] -52022.52
#> 
#> $xDot
#> [1] 33.27253
#> 
#> $yDot
#> [1] -8.646338
#> 
#> $zDot
#> [1] 95.54722
#> 
#> $h
#> [1] 16898.13
#> 
#> $f
#> [1] 54698.17
#> 
#> $i
#> [1] -72.00499
#> 
#> $d
#> [1] 68.77539
#> 
#> $hDot
#> [1] 3.985647
#> 
#> $fDot
#> [1] -89.64208
#> 
#> $iDot
#> [1] 0.03489031
#> 
#> $dDot
#> [1] -0.1157767
#> 

## Expected output
# x = 6117.5 nT
# y = 15751.9 nT
# z = -52022.5 nT
# xDot = 33.3 nT/yr
# yDot = -8.6 nT/yr
# zDot = 95.5 nT/yr
# h = 16898.1 nT
# f = 54698.2 nT
# i = -72 deg
# d = 68.78 deg
# hDot = 4.0 nT/yr
# fDot = -89.6 nT/yr
# iDot = 0.03 deg/yr
# dDot = -0.12 deg/yr

## Calculated output
#$x
#[1] 6117.548

#$y
#[1] 15751.91

#$z
#[1] -52022.52

#$xDot
#[1] 33.27253

#$yDot
#[1] -8.646338

#$zDot
#[1] 95.54722

#$h
#[1] 16898.13

#$f
#[1] 54698.17

#$i
#[1] -72.00499

#$d
#[1] 68.77539

#$hDot
#[1] 3.985647

#$fDot
#[1] -89.64208

#$iDot
#[1] 0.03489031

#$dDot
#[1] -0.1157767
```

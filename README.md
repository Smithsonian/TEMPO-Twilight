# TEMPO-Twilight
This repository provides inventory tables describing the content of TEMPO RADT twilight scans.
The inventory tables will be updated as reprocessed data become available.

The inventory records basic information for each granule, measures of geometric and radiometric 
quality, and indications of various phenomena likely to be contained therein.  It includes the 
exposure time, the geographic center, and the number of mirrors steps.  The lunar zenith angle 
is also provided at the granule center point with the lunar phase angle.

Summary table with additional notes following:

Variable | Definition | Units
--- |  --- | ---
Granule | RADT product filename | none
exposure | Detector exposure time | s
lat0 | Geographic latitude of granule center | degrees
lon0 | Geographic longitude of granule center | degrees
steps | Number of mirror steps in granule | none
reg_status | Success registering with VIIRS-DNB | logical
VIIRS_Ref | VIIRS product used as registration reference | none
verif_pnts | VIIRS registration verification point count | none
mu_dx | Mean residual registration error in the along-scan direction | pixels
mu_dy | Mean residual registration error in the cross-scan direction | pixels
sig_dx | One-sigma residual registration error in the along-scan direction | pixels
sig_dy | One-sigma residual registration error in the cross-scan direction | pixels
LPA | Lunar phase angle | degrees
LZA0 | Lunar zenith angle at granule center | degrees
solar_contam | Solar contaminated pixel count | none
aurora_pix | Pixel count with an aurora signature | none
lightning_pix | Pixel count with a lightning signature | none
mu_city_vis | Mean dark value in the CITY_VIS context image | nW/(cm^2 sr)
mu_city_uv | Mean dark value in the CITY_UV context image | nW/(cm^2 sr)
mu_full_vis | Mean dark value in the FULL_VIS context image | nW/(cm^2 sr)
mu_full_uv | Mean dark value in the FULL_UV context image | nW/(cm^2 sr)
mu_aurora | Mean dark value in the AURORA context image | nW/(cm^2 sr)
mu_lightning | Mean dark value in the LIGHTNING context image | nW/(cm^2 sr)
sig_city_vis | One-sigma dark value in the CITY_VIS context image | nW/(cm^2 sr)
sig_city_uv | One-sigma dark value in the CITY_UV context image | nW/(cm^2 sr)
sig_full_vis | One-sigma dark value in the FULL_VIS context image | nW/(cm^2 sr)
sig_full_uv | One-sigma dark value in the FULL_UV context image | nW/(cm^2 sr)
sig_aurora | One-sigma dark value in the AURORA context image | nW/(cm^2 sr)
sig_lightning | One-sigma dark value in the LIGHTNING context image | nW/(cm^2 sr)

TEMPO twilight radiances are registered to a VIIRS Day-Night Band
monthly clear-sky composite to assign accurate geographic coordinates
to spatial pixels.  The VIIRS registration status flag shows whether
registration was successful and against which VIIRS product the scan
was registered.  After registration, the quality is tested against the
same product, and the residual error statistics are placed in the
inventory.  Registration is by scan, so each granule belonging to a
particular scan will note the quality for the entire scan.

Dark target (ocean, unpopulated areas) pixels are identified in band
integrated radiances to characterize the radiometric quality of
imagery formed from various band integrations.  Dark target statistics
are put in the inventory for each of the context images that are
included in the RADT granules.  The context images are city lights
bands from the visible and UV, the full visible and UV bands, and
aurora and lightning bands.

Solar contaminated pixels are counted and put in the inventory.  Solar
contamination is defined as pixels with zenith angles less than 98
degrees.  Lightning and aurora pixel counts are included from those
pixels that are not solar contaminated.  These counts are indicative
of phenomena to be found in each granule but should not be considered
as scientifically validated.  Some lightning and aurora pixels to be
found at the end or beginning of observing seasons may be actually
solar contaminated pixels.  An aurora pixel has an aurora band
integrated radiance > 1 nW/(cm^2 sr) and is northwards of 50 degrees.
Lightning pixels are southwards of 50 degrees with radiances that are
six sigma above the mean.

For more on the L1 twilight radiance product, please consult the L1 product users guide.                                                                                           

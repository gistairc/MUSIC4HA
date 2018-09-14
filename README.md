#  MUSIC for HA dataset

## Overview

The **H**ot**A**rea(**HA**) is a system to automatically detect hotspots (e.g., fires and volcanoes) in the world in mid-resolution satellite data and displays the results on a web-based GIS system. Currently Hotarea utilizes Landsat 8 and Sentinel-2 data in global scale and in some selected regions, respectively.


The Landsat 8 Operational Land Imager (OLI) and Sentinel-2 Multispectral Instrument (MSI) are designed to observe solar radiance reflected by the land surface in the visible to shortwave infrared region, i.e., 0.43–2.3 μm. While the peak wavelength of solar radiance that corresponds to 6000 K is in the visible region (0.4–0.7 μm), the peak wavelength of hotspots such as fire corresponds to the shortwave infrared (SWIR, 1.3–3 μm) to midinfrared (3–8 μm) regions (Fig. 1). Therefore, at longer wavelengths, the radiance of a hotspot observed by the satellite sensor increases. Although the reflected spectral radiances in the near-infrared (NIR: 0.85 μm) and the SWIR (2.2 μm) regions correlate well on the ground surface, the SWIR radiance of a hotspot increases anomalously. Fig. 2 implies that an appropriate threshold distinguishes signals corresponding to hotspots from surface reflection. Hotarea uses this empirical characteristic to automatically detect hotspots in satellite images. 

![fig:Spectral radiance at various temperatures as a function of wavelength. B5–B11 are band numbers of Landsat 8.](https://github.com/gistairc/MUSIC4HA/blob/master/fig1.jpg "Spectral radiance at various temperatures as a function of wavelength. B5–B11 are band numbers of Landsat 8.")  
Fig1 : Spectral radiance at various temperatures as a function of wavelength. B5–B11 are band numbers of Landsat 8.

![fig: Example of the relationship between NIR and SWIR top-of-atmosphere reflectance.](https://github.com/gistairc/MUSIC4HA/blob/master/fig2.jpg "Example of the relationship between NIR and SWIR top-of-atmosphere reflectance.")  
Fig2 : Example of the relationship between NIR and SWIR top-of-atmosphere reflectance.

We classified the detection results into these categories (Fig.3.).  
Landsat-8 multiband images of these target areas were cropped into a 16 × 16 pixel from hot area detection point.

![fig: class](https://github.com/gistairc/MUSIC4HA/blob/master/fig3.jpg "Hot area categories")  
Fig3 : Hot area categories.

You can download the **MUSIC** for HA dataset with two different format Tiff along with the source code for the detection and classification. More detailed exaplanations can be found in the following papers.

 
[1] *加藤創史,神山徹,中村良介，"夜間Landsat 8 OLIデータによる高温熱源の温度推定"，日本リモートセンシング学会第59回(平成27年度秋季)学術講演会, 2015年11月   
[2]  *Kato. S, and Nakamura. R , "Detection of thermal anomaly using Sentinel-2A data", IEEE IGARSS 2017, July 2017.  
[3]  *Miyamoto.H, Kato.S, Oda.A, Nakamura.R ," Automatic Classification of Hot spots on Satellite Imagery by Deep Learning", JSAI 2017,May 2017  

## Download  
**IMPORTANT** -- Please read the [Terms of Use](https://github.com/gistairc/MUSIC4HA/blob/master/LICENSE.md) before downloading the MUSIC4HA dataset.

The dataset can be downloaded from [here](http://data.airc.aist.go.jp/MUSIC4HA/MUSIC4HA.zip) (12MB) .  
Or type the following in the terminal.  
```
$ wget http://data.airc.aist.go.jp/MUSIC4HA/MUSIC4HA.zip
$ unzip MUSIC4HA.zip
```
The directory configuration in the unzipped files is as follows:  
```
./resource/
train/
	fire/
		LC80010822015275LGN00_2710_dst.tif
		LC80050532015335LGN00_2823_dst.tif ...
	factory/
		LC80010772015275LGN00_3191_dst.tif
		LC80150282015213LGN00_2938_dst.tif ...
	valcano/
		LC80100612014303LGN00_1650_dst.tif
		LC80170512016086LGN00_1657_dst.tif ...
	oilplatform/
		LC82070182016185LGN00_2034_dst.tif
		LC82070182016185LGN00_2033_dst.tif 
	nontypable/
		LC80100602015274LGN00_1343_dst.tif
		LC80170412015275LGN00_2715_dst.tif ...
	roof/
		LC81150232015258LGN00_60_dst.tif
		LC81150272015258LGN00_20_dst.tif ...
	
val/
(same structure for train dir... )
test/
(same structure for train dir... )
```


## Acknowledgement
This dataset and source code are based on results obtained from a project commissioned by the New Energy and Industrial Technology Development Organization (NEDO).  

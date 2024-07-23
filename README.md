# Surface Biology and Geology (SBG) Observing Terrestrial Thermal Emission Radiometer (OTTER)

## SBG-TIR OTTER Level 3 Surface Mineralogy (L3-SM) Data Product Algorithm

[Michael S. Ramsey](https://github.com/michaelsramsey)<br>
[mramsey@pitt.edu](mailto:mramsey@pitt.edu)<br>
University of Pittsburgh

[James O. Thompson](https://github.com/jthompson2710)<br>
[james.thompson@beg.utexas.edu](mailto:james.thompson@beg.utexas.edu)<br>
University of Texas Austin

Federico Rabuffi (he/him)<br>
[federico.rabuffi@jpl.nasa.gov](mailto:federico.rabuffi@jpl.nasa.gov)<br>
NASA Jet Propulsion Laboratory 329A


# Abstract
The 2017-2027 Decadal Survey for Earth Science and Applications from Space (ESAS 2017) was released in January 2018. ESAS 2017 was driven by input from the scientific community and policy experts and provides a strategic vision for the next decade of Earth observation that informs federal agencies responsible for the planning and execution of civilian space-based Earth-system programs in the coming decade. These include the National Aeronautics and Space Administration (NASA), the National Oceanic and Atmospheric Administration (NOAA), and the U.S. Geological Survey (USGS). NASA has, thus far, utilized this document as a guide to inform exploration of new Earth mission concepts that are later considered as can-didates for fully funded missions. High-priority emphasis areas and targeted observables include global-scale Earth science questions related to hydrology, ecosystems, weather, climate, and solid earth. One of the Designated Observables (DO’s) identified by ESAS 2017 was Surface Biology and Geology (SBG) with a goal to acquire concurrent global hyperspectral visible to shortwave infrared (VSWIR; 380–2500 nm) and multispectral midwave and thermal infrared (MWIR: 3–5 μm; TIR: 8–12 μm) image data at high spatial resolution (~30 m in the VSWIR and ~ 60 m in the TIR) at sub-monthly temporal resolution globally. The final sensor characteristics will be determined during the mission formulation phase, but ESAS 2017 provides guidance for a VSWIR instrument with 30–45 m pixel resolution, ≤16 day global revisit, SNR > 400 in the VNIR, SNR > 250 in the SWIR, and 10 nm sampling in the range 380–2500 nm. It also recommends a TIR instrument with more than five channels in 8–12 μm, and at least one channel at 4 μm, ≤60 m pixel resolution, ≤3 day global revisit, and noise equivalent delta temperature (NEdT) ≤0.2 K (NASEM, 2018; Schimel et al., 2020). Alone, SBG will provide a comprehensive global monitoring for multiple scientific disciplines. Complemented with systems like Landsat and Sentinel-2 VSWIR, global change processes with faster than 16-day global change rates can be mapped. Further, complimented with planned TIR systems such as LSTM and TRISHNA, the temporal revisit could be as frequent as 1-day at the equator, making the system excellent for tracking dynamic thermal features and hazards. This document will grow to fully describe the planned Level-3 Surface Mineralogy (SM) product for the SBG TIR data.

_______________________________________________________________________________________________________________________
<i>This repository will gradually expand to contain the Surface Biology and Geology Thermal Infrared (SBG-TIR) OTTER level 3 surface mineralogy (L3-SM) data product algorithm.</i>
_______________________________________________________________________________________________________________________


## Level 3 Algorithm Theoretical Basis Document (ATBD): [click here](/SBG_L3_ATBD_SM_20231107.pdf)
## Level 3 Product Specification Document (PSD): [click here](/SBG-TIR_PSD_L3_SM_20231107.pdf)


##  1. Introduction

### 1.1. Identification

This is the Product Specification Document (PSD) for Level 3 (L3) Surface Mineralogy (SM) data product of NASA's Surface Biology and Geology -- Thermal Infrared (SBG-TIR) mission. The SBG-TIR L3 SM product provides surface minerology maps generated from data acquired by the SBG-TIR radiometer instrument according to the SM algorithm described in the SBG-TIR L3 SM Algorithm Theoretical Basis Document (ATBD) (D- 1000788).

### 1.2. Purpose and Scope

This PSD describes the standard Level 3 SM product generated using the SM algorithm. These include the detailed descriptions of the format and contents of the product and ancillary files that will be delivered to the Land Process Distributed Active Archive Center (LP-DAAC).

### 1.3.Mission Overview

NASA's SBG mission was a Designated Observable (DO) identified in the National Academies of Sciences, Engineering and Medicine (NASEM) 2017 Decadal Survey. The Decadal Survey document presented a clear vision for the combined roles of visible to shortwave infrared imaging spectroscopy and multispectral or hyperspectral thermal infrared image data in addressing terrestrial and aquatic ecosystems and other elements of biodiversity, geology, natural hazards, the water cycle, and applied sciences topics relevant to many areas with societal benefits. 

The SBG-TIR portion of the mission develops the IR multispectral instrument. The SBG-TIR instrument measures the emitted radiance of the Earth surface and uses that information to better understand the dynamics of Earth's changing surface geology and biology, ground/water temperature, snow reflectivity, active geologic processes, vegetation traits, and algal biomass.

SBG-TIR mission addresses the following most important and very important priorities as highlighted by the Decadal Survey:
highlighted by the Decadal Survey:
	
Most Important
Ecosystems
E1a: Quantify the distribution of the functional traits, functional types, and composition of vegetation and marine biomass, spatially and over time.
E1c: Quantify the physiological dynamics of terrestrial and aquatic primary producers.
E2a: Quantify the fluxes of CO2 and CH4 globally at spatial scales of 100 to 500 km and monthly temporal resolution with uncertainty <25% between land ecosystems and atmosphere and between ocean ecosystems and atmosphere.

Hydrology
H1c: Quantify rates of snow accumulation, snowmelt, ice melt, and sublimation from snow and ice worldwide at scales driven by topographic variability.

Solid Earth
S1a: Measure the pre-, syn-, and post eruption surface deformation and products of Earth’s entire active land volcano inventory at a time scale of days to weeks.

Very Important
Ecosystems
E1a: Quantify the distribution of the functional traits, functional types, and composition of vegetation and marine biomass, spatially and over time.

Hydrology
H2a: Quantify how changes in land use, water use, and water storage affect evapotranspiration rates, and how these in turn affect local and regional precipitation systems, groundwater recharge, temperature extremes, and carbon cycling.
H4a: Monitor and understand hazard response in rugged terrain and land margins to heavy rainfall, temperature and evaporation extremes, and strong winds at multiple temporal and spatial scales. This socioeconomic priority depends on success of addressing H1b and H1c, H2a, and H2c.

Solid Earth
S1c: Forecast and monitor landslides, especially those near population centers.
S2b: Assess surface deformation (<10 mm), extent of surface change (<100 m spatial resolution) and atmospheric contamination, and the composition and temperature of volcanic products following a volcanic eruption (hourly to daily temporal sampling).

Climate
C3a: Quantify CO2 fluxes at spatial scales of 100-500 km and monthly temporal resolution with uncertainty <25% to enable regional-scale process attribution explaining year-to-year variability by net uptake of carbon by terrestrial ecosystems (i.e., determine how much carbon uptake results from processes such as CO2 and nitrogen fertilization, forest regrowth, and changing ecosystem demography.)

Weather
W3a: Determine how spatial variability in surface characteristics modifies regional cycles of energy, water and momentum (stress) to an accuracy of 10 W/m2 in the enthalpy flux, and 0.1 N/m2 in stress, and observe total precipitation to an average accuracy of 15% over oceans and/or 25% over land and ice surfaces averaged over a 100 × 100 km region and 2- to 3-day time period.

The SBG-TIR mission answers these questions by accurately measuring the emitted radiance of Earth’s surface in the mid-infrared (MIR) and TIR spectral regions using a multispectral radiometer. The instrument measures radiance data in 8 spectral bands from 3.95 to 12.05 μm with approximately 60 meter spatial resolution at nadir and a nominal revisit time of 3 days at the equator.

### 1.4. Applicable and Reference Documents

"Applicable" documents levy requirements on the areas addressed in this document. "Reference" documents are identified in the text of this document only to provide additional information to readers. Unless stated otherwise, the document revision level is Initial Release. Document dates are not listed, as they are redundant with the revision level.

#### 1.4.1. Applicable Documents

SBG-TIR Science Data Management Plan (TBD)

SBG-TIR Level 1 Algorithm Theoretical Basis Documents (TBD)

SBG-TIR Level 1 Algorithm Specification Document (TBD)

SBG-TIR Level 2 Algorithm Theoretical Basis Documents (TBD)

SBG-TIR Level 2 Algorithm Specification Document (TBD)

SBG-TIR Project Level 3 Science Data System Requirements (TBD).

SBG-TIR Level 3 SM Algorithm Theoretical Basis Document (TBD)

#### 1.4.2. Reference Documents

2017-2027 Decadal Survey for Earth Science and Applications from Space (ESAS 2017)

SBG Science and Applications Traceability Matrix (SATM)

### 1.5. SBG-TIR Data Products

SBG-TIR Level 0 data include spacecraft packets that have been pre-processed by the Ground Data System (GDS). Level 1 products include spacecraft engineering data, the time-tagged raw sensor pixels appended with their radiometric calibration coefficients, the blackbody pixels used to generate the calibration coefficients, geolocated and radiometrically calibrated at-sensor radiances of each image pixel, the geolocation tags of each pixel, and the corrected spacecraft attitude data. Level 2 products include the visible near infrared top of atmosphere (VNIR TOA) reflectance, VNIR bottom of atmosphere (BOA) reflectance, the normalized difference vegetation index (NDVI), the surface temperature and emissivity of each spectral band retrieved from the at-sensor radiance data, and a cloud mask. Level 3 products include evapotranspiration, elevated temperature features, and surface minerology data derived from Level 2 data. Level 4 products contain evaporative stress index, water use efficiency, and volcanic activity derived from Level 2 and 3 data.

The four levels of data products are listed in Table 1-1. This document will discuss only the Level 3 SM product.

Table 1-1: SBG-TIR Product Groups ![Graphical user interface, table
Description automatically generated with medium confidence](./media/image2.png){width="4.997222222222222in" height="2.584722222222222in"}

[]{#_Toc150275586 .anchor}

## 2. Data Product Organization

### 2.1. Product File Format

All SBG-TIR standard products are stored in the Geographic Tagged Image File Format (GeoTIFF). GeoTIFF is a general purpose file format and programming library for storing scientific data. The GeoTIFF format was originally created by Dr. Niles Ritter with the Open Geospatial Consortium publishing the OGC GeoTIFF standard, which defines the GeoTIFF by specifying requirements and encoding rules for using the Tagged Image File Format (TIFF) for the exchange of georeferenced or geocoded image data. The following sections provide some key elements of GeoTIFF that will be employed in SBG-TIR data products. Complete documentation of the GeoTIFF structure and application software can be found at https://www.ogc.org/standard/geotiff/.

### 2.2. GeoTIFF Notation

The key concepts of the GeoTIFF Abstract Data Model are Files, Groups, Datasets, Datatypes, Attributes and Property Lists. The following sections provide a brief description of each of these key GeoTIFF concepts.

#### 2.2.1. GeoTIFF File

A File is the abstract representation of a physical data file. Files are containers for GeoTIFF Objects. These Objects include Groups, Datasets, and Datatypes.

#### 2.2.2.GeoTIFF Group

Groups are containers for other Objects, including Datasets, named Datatypes and other Groups. In that sense, groups are analogous to directories that are used to categorize and classify files in standard operating systems.

The notation for files is identical to the notation used for Unix directories. The root Group is "/". Like Unix directories, Objects appear in Groups through "links". Thus, the same Object can simultaneously be in multiple Groups.

#### 2.2.3. GeoTIFF Dataset

The Dataset is the GeoTIFF component that stores user data. Each Dataset associates with a Dataspace that describes the data dimensions, as well as a Datatype that describes the basic unit of storage element. A Dataset can also have Attributes.

#### 2.2.4. GeoTIFF Datatype

A Datatype describes a unit of data storage for Datasets and Attributes. Datatypes are subdivided into Atomic and Composite Types.

Atomic Datatypes are analogous to simple basic types in most programming languages. GeoTIFF Atomic Datatypes include Time, Bitfield, String, Reference, Opaque, Integer, and Float. Each atomic type has a specific set of properties. Examples of the properties associated with Atomic Datatypes are:

-   Integers are assigned size, precision, offset, pad byte order, and are designated as signed or unsigned.

-   Strings can be fixed or variable length and may or may not be null terminated.

-   References are constructs within GeoTIFF Files that point to other GeoTIFF Objects in the same file.

GeoTIFF provides a large set of predefined Atomic Datatypes. Table 2-1 lists the Atomic Datatypes that are used in SBG-TIR data products.

| **GeoTIFF Atomic Datatypes** | **Description** | 
| --- | --- |
| BYTE | unsigned, 8-bit, little-endian integer | 
| SHORT | unsigned, 16-bit, little-endian integer | 
| LONG | unsigned, 32-bit, little-endian integer | 
| RATIONAL | 2 unsigned, 8-bit, little-endian integer | 
| SBYTE | signed, 16-bit, little-endian integer | 
| SSHOR | signed, 32-bit, little-endian integer | 
| SLONG | signed, 32-bit, little-endian integer | 
| SRATIONAL | 2 signed, 32-bit, little-endian integer | 
| FLOAT | 32-bit, little-endian, IEEE floating point | 
| DOUBLE | 64-bit, little-endian, IEEE floating point | 
| ASCII | NULL terminated string | 
| UNDEFINED | 8-bit byte | 

*Table 2-1: GeoTIFF Atomic Datatypes*


Composite Datatypes incorporate sets of Atomic datatypes. Composite Datatypes include Array, Enumeration, Variable Length and Compound.

The Array Datatype defines a multi-dimensional array that can be accessed atomically.

Variable Length presents a 1-D array element of variable length. Variable Length Datatypes are useful as building blocks of ragged arrays.

Named Datatypes are explicitly stored as Objects within an GeoTIFF File. Named Datatypes provide a means to share Datatypes among Objects. Datatypes that are not explicitly stored as Named Datatypes are stored implicitly. They are stored separately for each Dataset or Attribute they describe.

None of the SBG-TIR data products employ Enumeration or Compound data types.

### GeoTIFF Dataspace

A Dataspace describes the rank and dimension of a Dataset or Attribute. For example, a "Scalar" Dataspace has a rank of 1 and a dimension of 1. Thus, all subsequent references to "Scalar" Dataspace in this document imply a single dimensional array with a single element.

Dataspaces provide considerable flexibility to GeoTIFF products. They incorporate the means to subset associated Datasets along any or all of their dimensions. When associated with specific properties, Dataspaces also provide the means for Datasets to expand as the application requires.

### GeoTIFF Attribute

An Attribute is a small aggregate of data that describes Groups or Datasets. Like Datasets, Attributes are also associated with a particular Dataspace and Datatype. Attributes cannot be subsetted or extended. Attributes themselves cannot have Attributes.

[]{.mark}

## SBG-TIR File Organization

### Structure

SBG-TIR data products follow a common convention for all GeoTIFF Files. Use of this convention provides uniformity of data access and interpretation.

The SBG-TIR Project uses GeoTIFF Groups to provide an additional level of data organization. All metadata that pertain to the complete data granule are members of the "/Metadata" Group. All other data are organized within Groups that are designed specifically to handle the structure and content of each particular data product.

### Data

All data in GeoTIFF files are stored in individual Datasets. All related Datasets in an SBG-TIR product are assigned to an GeoTIFF Group. A standard field name is associated with each Dataset. The field name is a unique string identifier. The field name corresponds to the name of the data element the Dataset stores. This document lists these names with the description of each data element that they identify.

Each Dataset is associated with an GeoTIFF Dataspace and an GeoTIFF Datatype. They provide a minimally sufficient set of parameters for reading the data using standard GeoTIFF tools.

### Element Types

SBG-TIR GeoTIFF employs the Data Attribute "Type" to classify every data field as a specific data type. The "Type" is an embellishment upon the standard GeoTIFF Datatypes that is designed specifically to configure SBG-TIR data products.

Table 2-2 lists all of the "Type" strings that appear in the SBG-TIR data products. The table maps each SBG-TIR "Type" to a specific GeoTIFF Datatype in both the GeoTIFF file and in the data buffer. The table also specifies the common conceptual data type that corresponds to the "Type" in SBG-TIR executable code.

|**Type** | **GeoTIFF Datatype (File)** | **GeoTIFF Datatype (Buffer)** | **Concetual Type** | 
| --- | --- | --- | --- |
| Unsigned8 | BYTE | | unsigned integer |
| NULL-terminated8 | ASCII | | unsigned integer |
| Unsigned16 | SHORT | | unsigned integer |
| Unsigned32 | LONG | | unsigned integer |
| 2 Unsigned32 | RATIONAL | | unsigned integer |
| Signed8 | SBYTE | | unsigned integer |
| 8-bit | UNDEFINE | | unsigned integer |
| Signed16 | SSHORT | | unsigned integer |
| Signed32 | SLONG | | unsigned integer |
| 2 Signed32 | SRATIONAL | | unsigned integer |
| Float32 | FLOAT | | unsigned integer |
| Float64 | DOUBLE | | unsigned integer |
*Table 2-2: Element Type Definitions*


### File Level Metadata

All metadata that describe the full content of each granule of the SBG-TIR data product are stored within the explicitly named "/Metadata" Group. Metadata are handled using exactly the same procedures as those that are used to handle data. The contents of each Attribute that stores metadata conform to one of the SBG-TIR Types. Most metadata elements are stored as scalars. A few metadata elements are stored as arrays. The metadata appear in a set of GeoTIFF Groups under the "/Metadata" Group. These GeoTIFF Groups contain a set of GeoTIFF Attributes.

### Local Metadata

SBG-TIR standards incorporate additional metadata that describe each GeoTIFF Dataset within the GeoTIFF file. Each of these metadata elements appear in an GeoTIFF Attribute that is directly associated with the GeoTIFF Dataset. Wherever possible, these GeoTIFF Attributes employ names that conform to the Climate and Forecast (CF) conventions. Table 2-3 lists the CF names for the GeoTIFF Attributes that SBG-TIR products typically employ.

| **CF Compliant Attribute Name** | **Description** | **Required?** | 
| --- | --- | --- |
| Units | Units of measure.  Appendix A lists applicable units for various data elements in this product. | Yes |
| valid_max | The largest valid value for any element in the Dataset.  The data type in valid_max matches the type of the associated Dataset.  Thus, if the associated Dataset stores float32 values, the corresponding valid_max will also be float32. | No |
| valid_min | The smallest valid value for any element in the Dataset.  The data type in valid_min matches the type of the associated Dataset.  Thus, if the associated Dataset stores float32 values, the corresponding valid_min will also be float32. | No |
| _FillValue | Specification of the value that will appear in the Dataset when an element is missing or undefined.  The data type of _FillValue matches the type of the associated Dataset.  Thus, if the associated Dataset stores float32 values, the corresponding _FillValue will also be float32. Datasets that do not have a fill value will omit this attribute. | No |
| long_name | A descriptive name that clearly describes the content of the associated Dataset. | Yes |

*Table 2-3: SBG-TIR Specific Local Attributes*

## Data Definition Standards 

The following sections of this document specify the characteristics and definitions of every data element stored in the SBG-TIR data products. Table 2-4 defines each of the specific characteristics that are listed in those sections. Some of these characteristics correspond with the SBG-TIR GeoTIFF Attributes that are associated with each Dataset. Data element characteristics that correspond to SBG-TIR GeoTIFF Attributes bear the same name. The remaining characteristics are descriptive data that help users better understand the data product content.

In some situations, a standard characteristic may not apply to a data element. In those cases, the field contains the character string 'n/a'. Hexadecimal representation sometimes indicates data content more clearly. Numbers represented in hexadecimal begin with the character string '0x'.

| **Characteristic** | **Definition** |
| --- | --- |
| Type | The data representation of the element within the storage medium. The storage class specification must conform to a valid SBG type. |
| Units | Units of measure.  Typical values include “deg”, “degC”, “Kelvin”, “meters/second”, “meters”, “m**2”, “seconds” and “counts”.  Appendix A includes references to important data measurement unit symbols. |

*Table 2-4: Data Element Characteristic Definitions*

### Double Precision Time Variables

SBG-TIR double precision time variables contain measurements relative to the J2000 epoch. Thus, these variables represent a real number of Standard International (SI) compatible seconds since 11:58:55.816 on January 1, 2000 UTC.

### Array Representation

This document employs array notation to demonstrate and clarify the correspondence among data elements in different product data elements. The array notation adopted in this document is similar to the standards of the Fortran programming language. Indices are one based. Thus, the first index in each dimension is one. This convention is unlike C or C++, where the initial index in each dimension is zero. In multidimensional arrays, the leftmost subscript index changes most rapidly. Thus, in this document, array elements ARRAY(15,1,5) and ARRAY(16,1,5) are stored contiguously.

GeoTIFF is designed to read data seamlessly regardless of the computer language used to write an application. Thus, elements that are contiguous using the dimension notation in this document will appear in contiguous locations in arrays for reading applications in any language with an GeoTIFF interface.

This document differentiates among array indices based on relative contiguity of storage of elements referenced with consecutive numbers in that index position. A faster or fastest moving index implies that the elements with consecutive numbers in that index position are stored in relative proximity in memory. A slower or slowest moving index implies that the elements referenced with consecutive indices are stored more remotely in memory. For instance, given array element ARRAY(15,1,5) in Fortran, the first index is the fastest moving index, and the third index is the slowest moving index. On the other hand, given array element array\[4\]\[0\]\[14\] in C, the first index is the slowest moving index, and the third index is the fastest moving index.

# [SBG-TIR PRODUCT FILES]{.smallcaps}

The SBG-TIR product file will contain at least 3 groups of data: A standard metadata group that specifies the same type of contents for all products, a product specific metadata group that specifies those metadata elements that are useful for defining attributes of the product data, and the group(s) containing the product data. (Note: A product metadata is not to be confused with a GeoTIFF object metadata.)

All product file names will have the form:

SBG-TIR_<PROD_TYPE>_<OOOOO>_<SSS>_<YYYYMMDDThhmmss>_<BBbb>_<VV>.<TYPE>

Where:

PROD_TYPE: Product type =
L1B_GEO, Geolocation parameters and at-sensor calibrated radiances 
L1C_RAD, Gridded radiance at sensor 
L1C_VNIR, Gridded radiance at sensor (VNIR)
L2_LSTE, Land Surface temperature and emissivity
L2_CLOUD, Cloud mask
L2_VNIR_TOA, VNIR TOA reflectance 
L2_VNIR_BOA, VNIR BOA reflectance
L2_NDVI, NDVI 
L3_ET, Evapotranspiration retrieved 
L3_ETF, Elevated Temperature Features
L3_SM, Surface Minerology
L4_ESI, Evaporative Stress Index
L4_WUE, Water Use Efficiency
L4_VA, Volcanic Activity
OOOOO: Orbit number; starting at start of mission, ascending equatorial crossing
SSS: Scene ID; starting at first scene of each orbit
YYYYMMDDThhmmss: Starting time of scene
BBbb: Build ID of software that generated product, Major+Minor (2+2 digits)
VV: Product version number (2 digits)
TYPE: File type extension=
.tif, for the data file
.tif.xml, for the metadata file


## Standard Metadata

This is the minimal set of metadata that must be included with each product file. The standard metadata consists of the following:

| **Name** | **Type** | **Size** | **Example** |
| --- | --- | --- | --- |
| AncillaryInputPointer | String | variable | Group name of ancillary file list | 
| AutomaticQualityFlag | String | variable | PASS/FAIL (of product data) |
| BuildId | String | variable | |
| CollectionLabel | String | variable | |
| DataFormatType | String | variable | NCSAHDF5 |
| DayNightFlag | String | variable | |
| EastBoundingCoordinate | LongFloat | 8 | |
| HDFVersionId | String | variable | 1.8.16 |
| ImageLines | Int32 | 4 | 5632 |
| ImageLineSpacing | Float32 | 4 | 68.754 | 
| ImagePixels | Int32 | 4 | 5400 |
| ImagePixelSpacing | Float32 | 4 | 65.536 |
| InputPointer | String | variable | |
| InstrumentShortName | String | variable | SBG |
| LocalGranuleID | String | variable | --- |
| LongName | String | variable | SBG |
| InstrumentShortName | String | variable | --- |
| LocalGranuleID | String | variable | --- |
| LongName | String | variable | SBG |
| NorthBoundingCoordinate | LongFloat | 8 | --- |
| PGEName | String | variable | L2_LSTE (L2_CLOUD) |
| PGEVersion | String | variable | |
| PlatformLongName | String | variable | |
| PlatformShortName | String | variable | |
| PlatformType | String | variable | Spacecraft |
| ProcessingLevelID | String | variable | 1 |
| ProcessingLevelDescription | String | variable | Level 2 Land Surface Temperatures and Emissivity (Level 2 Cloud mask) |
| ProducerAgency | String | variable | JPL |
| ProducerInstitution | String | variable | Caltech |
| ProductionDateTime | String | variable | |
| ProductionLocation | String | variable | |
| CampaignShortName | String | variable | Primary |
| RangeBeginningDate | String | variable | |
| CampaignShortName | String | variable | |
| RangeBeginningDate | String | variable | |
| RangeBeginningTime | String | variable | |
| RangeEndingDate | String | variable | |
| RangeEndingTime | String | variable | |
| SceneID | String | variable | |
| ShortName | String | variable | L2_LSTE (L2_CLOUD) |
| SceneID | String | variable | |
| ShortName | String | variable | |
| SISName | String | variable | |
| SISVersion | String | variable | |
| SouthBoundingCoordinate | LongFloat | 8 | |
| StartOrbitNumber | String | variable | |
| StartOrbitNumber | String | variable | |
| WestBoundingCoordinate | LongFloat | 8 | |

*Table 3-1: Standard Product Metadata*

## Product-Specific Metadata

Any additional metadata necessary for describing the product will be recorded in this group.

Table 3-2: Product Specific Metadata

| **Name** | **Type** | **Size** | **Example** |
| --- | --- | --- | --- |
| QualityBitFlag | Int   | 255  | 01011011011 |
| AvgETUncertainty  | Float | 8 |  |
| AncillaryFiles  | Int | 4 | 100   |
| AncillaryFileAirTemperature | String | 255  | CFSR_FILENAME_DATE |
| AncillaryFileSMid      | String  | 255  | EDAY_V7NC_CFSRINSOL_2018200.dat |
| AncillaryFileBadMask   | String  | 255  |    |
| AncillaryFileInsolation | String  | 255  | CFSR_FILENAME_DATE  |
| AncillaryFileLandcover | String  | 255  | NLCD_FILENAME |
| AncillaryFileLST       | String  | 255  | LSTE_FILENAME  |
| AncillaryFileMixingRatio   | String | 255  | CFSR_FILENAME_DATE   |
| AncillaryFilePressure  | String  | 255  | CFSR_FILENAME_DATE    |
| AncillaryFileSurfaceReflectance | String | 255  | LANDSAT_TARFILE_NAME  |
| AncillaryFileSurfReflectanceFill | String | 255  |   |
| AncillaryFileWindSpeed | String | 255  | CFSR_FILENAME_DATE  |
| BandSpecification | Float32 | 8    |   |
| Projection | String | 255  | (SBG-TIR or UTM) |
| Geotransform | String  | 255  | |
| OGC Well Known Text | String | variable | Blank if Projection=SBG-TIR
If Projection=UTM, EG:
{PROJCS["UTM_Zone_11N",GEOGCS["GCS_WGS_1984",DATUM["D_WGS_1984",SPHEROID["WGS_1984",6378137.0,298.257223563]],PRIMEM["Greenwich",0.0],UNIT["Degree",0.0174532925199433]],PROJECTION["Transverse_Mercator"],PARAMETER["False_Easting",500000.0],PARAMETER["False_Northing",0.0],PARAMETER["Central_Meridian",-117.0],PARAMETER["Scale_Factor",0.9996],PARAMETER["Latitude_Of_Origin",0.0],UNIT["Meter",1.0]]} |


## Product Data

The product data will be stored in this group. Exact contents and layouts to be defined by each PGE and will conform to the GeoTIFF specifications.

             
| **Field Name** | **Type** | **Unit** |
| --- | --- | --- |
| Amphibole Percentage | Int8 | 0-100 |
| Carbonate Percentage | Int8 | 0-100 |
| Mica Percentage | Int8 | 0-100 |
|  Olivine Percentage | Int8 | 0-100 |
| Plagioclase Feldspar Percentage | Int8 | 0-100 |
| Potassium Feldspar Percentage | Int8 | 0-100 |
| Pyroxene Percentage | Int8 | 0-100 |   
| Quartz Percentage  | Int8 | 0-100 |   
| Sulfate Percentage  | Int8 | 0-100 |   
| Blackbody Percentage  | Int8 | 0-100 |   
| Band 1 Residual Error | Float16 | 0-100 |   
| Band 2 Residual Error | Float16 | 0-100 |   
| Band 3 Residual Error | Float16 | 0-100 |   
| Band 4 Residual Error | Float16 | 0-100 |   
| Band 5 Residual Error | Float16 | 0-100 |   
| Band 6 Residual Error | Float16 | 0-100 |   
| RMS Error | Float16 | 0-100 |       
| Wt Perc Silica | Uint8 | 0-100 | 
| Data Quality | int8 |  | 

*Table 3-3: Product Data Definitions*

## Product Metadata File

The product metadata for each product file will be generated by the PCS from the metadata contents of each product file. The metadata will be converted into extensible markup language (XML). These will be used by the DAAC for cataloging. Exact contents and layout to be defined by PCS.

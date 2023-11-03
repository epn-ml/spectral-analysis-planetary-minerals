# Extraction form RELAB database
- from specimen_sheet (file: specimen_sheet.xlsx) extracted the column:
  - specimen_id (index: 1)
  - specimen_name (index: 3)
  - min_size (index: 5)
  - max_size (index: 6)
  - size_units (index: 7)
  - common_name (index: 28):
    - this field is input to filter program 
    
- from spectra_sheet (file: spectra_sheet.xlsx)
  - saved as csv the sheets:
    - spectrum_bd-vnir2Column.csv
    - spectrum_bd-vniri3Column.csv

## Filter program
After saved as csv the "Specimen List" sheet from Excel program, it is applied the filter:
- selected all rows that contains the words:
  - Plagioclase
  - Olivine
  - Pyroxene
- Based on the preceding lines, we have excluded specific lines that exhibited uncertain stored criteria.

## Spectral resampling
The spectral data is resampled to a wavelength interval of 1 nanometer. 

# Result
The resulting database consist of 629 spectral in json format, with the following structure:
- spectrum
  - wavelength: this is an array of wavelength in nanometer unit
  - reflectance: the spectral reflectance adimentional (? C.Carli confermi??)
  - error: The standard deviation of reflectance is calculated when applicable; otherwise, a value of -1.0 indicates that no error calculation was performed.
- grain_size (If both the minimum and maximum values are null, it indicates that information regarding the grain size is not available.)
  - min: The minimum value of grain size
  - max: The maximum value of grain size
  - unit: Unit of grain size measurement 
- abundances
  - mineral_phase_name (scrivere qualcosa C.Carli)
  - percentage (scrivere qualcosa C. Carli)
- description: "Spectrum downloaded from RELAB Spectral Database",
- version: dataset version.

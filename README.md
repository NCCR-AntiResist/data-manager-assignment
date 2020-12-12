## Long read sequencing of carbapenemase producing bacteria

This data set consists of genome sequencing data of multi-resistant bacteria.
These were sequenced using Illumina technology at the USB and using long-read nanopore technology at the Biozentrum.
In addition, resistance data are available for these strains.
The raw data have been deposited in public archives at [NCBI under BioProject PRJEB28660](https://www.ncbi.nlm.nih.gov/bioproject/PRJEB28660).

We need a data organization that links

  * The resistance information
  * the Illumina data
  * the nanopore data
  * the assemblies
  * the records on SRA

### [illumina_data.tree](illumina_data.tree)

This file contains the directory listing of the trimmed short reads.
The sample number is the first part of the file name.
Files ending on `_R1_001_val_1.fq.gz` are read 1, files ending on `_R2_001_val_2.fq.gz` are read 2.


### [nanopore_data.tree](nanopore_data.tree)

This file contains the nanopore runs.
Each run is labeled by the date in as `%Y%m%s`.
Each folder contains the processed reads by barcode as `BC{%02d}.fasta.gz` where the placeholder is the barcode number.

### [sample_table.csv](sample_table.csv)

This file contains the relevant linking information.
The header line is
```
Internal #,Isolate #,Species,Labor Number,Date,Box,Platz,DNA Konzentration,sequenced,mb,barcode,resequenced,rebarcode
```

where `Internal #` is our consecutive index that is used to refer to the strains as `carb001` etc.
`Labor Nummer` is the number used to label the illumina data.
`sequenced` and `barcode` are the fields that identify the nanopore data.
Some samples have been resequenced on nanopore, these are labeled as `resequenced` and `rebarcode` are the fields that identify the nanopore data.

Note that the sample table only contains a subset of the strains.
Fine to focus on these for now.

### [MIC_data.csv](MIC_data.csv)

This fule contains more meta data such as species as well as resistance information.



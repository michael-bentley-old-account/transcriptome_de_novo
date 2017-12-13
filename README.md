# Transcriptome de novo  
A pipeline for de novo transcriptome construction and analysis.

## FastQValidator [(Manual)](https://genome.sph.umich.edu/wiki/FastQValidator)
The fastQValidator validates the format of fastq files.

## FastQC [(Manual)](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/) 
FastQC aims to provide a simple way to do some quality control checks on raw sequence data coming from high throughput sequencing pipelines. 

## sortmerna [(Manual)](https://github.com/biocore/sortmerna/blob/master/README.md) 
SortMeRNA is a local sequence alignment tool for filtering, mapping and clustering.

## Trinity [(Manual)](https://github.com/trinityrnaseq/trinityrnaseq/wiki) 
Trinity, developed at the Broad Institute and the Hebrew University of Jerusalem, represents a novel method for the efficient and robust de novo reconstruction of transcriptomes from RNA-seq data. 

## Trinotate [(Manual)](https://trinotate.github.io/) 
Trinotate is a comprehensive annotation suite designed for automatic functional annotation of transcriptomes, particularly de novo assembled transcriptomes, from model or non-model organisms.



##### Build sqlite databases
I modified the original `Build_Trinotate_Boilerplate_SQLite_db.pl` script in order to be able to obtain two different databases. One for searching the compact Swiss-Prot database, the other for searching the much larger TrEMBL database. 

```
Build_Trinotate_Boilerplate_SQLite_db_sprot.pl Trinotate_sprot
Build_Trinotate_Boilerplate_SQLite_db_trembl.pl Trinotate_trembl
```

##### Build BLAST databases
```
makeblastdb -in uniprot_sprot.fasta -dbtype prot
makeblastdb -in uniprot_trembl.fasta -dbtype prot
```
##### Build DIAMOND databases
```
diamond makedb --in uniprot_sprot.fasta -d uniprot_sprot -p 32
diamond makedb --in uniprot_trembl.fasta -d uniprot_sprot -p 32
```

## DIAMOND [(Manual)](https://github.com/bbuchfink/diamond) 
DIAMOND is a sequence aligner for protein and translated DNA searches and functions as a drop-in replacement for the NCBI BLAST software tools. It is suitable for protein-protein search as well as DNA-protein search on short reads and longer sequences including contigs and assemblies, providing a speedup of BLAST ranging up to x20,000. 

## Appendix


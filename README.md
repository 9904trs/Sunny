# STAR Genomeindex
------------------------------
## Materials
#### Reference fasta :

* Genconde Release 34 GRch38.primary_assembly.genome.fa.gz

        wget ftp://ftp.ebi.ac.uk/pub/databases/gencode/Gencode_human/release_34/GRCh38.primary_assembly.genome.fa.gz


#### Reference gtf file :

* Gencode Release 34 annotation.gtf

        wget ftp://ftp.ebi.ac.uk/pub/databases/gencode/Gencode_human/release_34/gencode.v34.annotation.gtf.gz
        gzip -d gencode.v34.annotation.gtf.gz

## Generating genome indexes

#### Reference fasta indexing :
        
        cd ./reference_fasta/path
        gzip -d GRCh38.primary_assembly.genome.fa.gz
        bowtie2-build GRCh38.primary_assembly.genome.fa GRCh38.primary_assembly.genome --threads 4
        
#### STAR genomeGenerate :

        ./install/path/STAR --runThreadN 4 --runMode genomeGenerate --genomeDir ./output/dir --genomeFastaFiles ./reference/dir/GRCh38.primary_assembly.genome.fa --sjdbGTFfile ./GTF/dir/gencode.v34.annotation.gtf.gz 
        
#### STAR alignment :


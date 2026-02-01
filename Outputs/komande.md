# komande.md

*Ve�ba 6*

## >>> README.md

### 1.5 - 1.9 - uneti komande

```bash
#Zadatak 1
conda activate kleborate
kleborate --versionmkdir -p data/genomes data/annotations
tree data
sudo apt install tree
tree data
data
├── annotations
└── genomes
tar -xzvvf za_vezbe_Klebsiella_sekvence.tar.gz
cd za_vezbe_Klebsiella_sekvence
(kleborate) sandra@sandra-ubuntu-24:~/Documents/lab-sandrastojadinovic/vezba6-Sandra242424/za_vezbe_Klebsiella_sekvence$ ls
GCF_017743115.fna  GCF_017815715.fna  GCF_021442005.fna  GCF_902723705.fna
GCF_017743115.gff  GCF_017815715.gff  GCF_021442005.gff  GCF_902723705.gff
GCF_017743135.fna  GCF_021057265.fna  GCF_902723695.fna  GCF_902827215.fna
GCF_017743135.gff  GCF_021057265.gff  GCF_902723695.gff  GCF_902827215.gff
(kleborate) sandra@sandra-ubuntu-24:~/Documents/lab-sandrastojadinovic/vezba6-Sandra242424/za_vezbe_Klebsiella_sekvence$ mv *.fna ../data/genomes/
(kleborate) sandra@sandra-ubuntu-24:~/Documents/lab-sandrastojadinovic/vezba6-Sandra242424/za_vezbe_Klebsiella_sekvence$ mv *.gff ../data/annotations/
(kleborate) sandra@sandra-ubuntu-24:~/Documents/lab-sandrastojadinovic/vezba6-Sandra242424/za_vezbe_Klebsiella_sekvence$ cd ..
(kleborate) sandra@sandra-ubuntu-24:~/Documents/lab-sandrastojadinovic/vezba6-Sandra242424$ tree data
data
├── annotations
│   ├── GCF_017743115.gff
│   ├── GCF_017743135.gff
│   ├── GCF_017815715.gff
│   ├── GCF_021057265.gff
│   ├── GCF_021442005.gff
│   ├── GCF_902723695.gff
│   ├── GCF_902723705.gff
│   └── GCF_902827215.gff
└── genomes
    ├── GCF_017743115.fna
    ├── GCF_017743135.fna
    ├── GCF_017815715.fna
    ├── GCF_021057265.fna
    ├── GCF_021442005.fna
    ├── GCF_902723695.fna
    ├── GCF_902723705.fna
    └── GCF_902827215.fna

3 directories, 16 files
kleborate \
> -- input data/genomes \
> --output results/kleborate_results.tsv \ 
kleborate \
> -a data/genomes/*.fna \
> -o results/kleborate_results.tsv
less results/kleborate_resul
mkdir -p results
kleborate -a data/genomes/*.fna -o results/kleborate_results.tsv
cd Outputs

```

---

#Zadtak2
mkdir -p klebsiella_genome
cd klebsiella_genome
wget https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/021/057/265/GCF_021057265.1_ASM2105726v1/GCF_021057265.1_ASM2105726v1_genomic.fna.gz
wget https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/021/057/265/GCF_021057265.1_ASM2105726v1/GCF_021057265.1_ASM2105726v1_genomic.gff.gz
wget https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/021/057/265/GCF_021057265.1_ASM2105726v1/md5checksums.txt
gunzip -k GCF_021057265.1_ASM2105726v1_genomic.fna.gz
gunzip -k GCF_021057265.1_ASM2105726v1_genomic.gff.gz
grep "genomic.fna.gz" md5checksums.txt > genome_compressed.txt
md5sum GCF_021057265.1_ASM2105726v1_genomic.fna.gz

#Zadatak3

cd klebsiella_genome
mkdir -p genomes annotations
mv *.fna genomes/
mv *.gff annotations/

cd ..
tar -czvf klebsiella_archive.tar.gz klebsiella_genome
tar -tzvf klebsiella_archive.tar.gz


#Zadatak4
mkdir -p scripts
nano scripts/klebsiella_download_archive.sh
chmod +x scripts/klebsiella_download_archive.sh
cd scripts
./klebsiella_download_archive.sh
tree klebsiella_genome

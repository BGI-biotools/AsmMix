# AsmMix

AsmMix is capable of producing both contiguous and accurate diploid genomes. It first assembles co-barcoded reads to generate accurate haplotype-resolved assemblies that may contain many gaps, while the long-read assembly is contiguous but susceptible to errors. Then those two sets of sequences are compared and integrated into a haplotype-resolved assembly with reduced errors. 

![Image text](https://github.com/BGI-tianjin-dev/AsmMix/blob/main/AsmMix/figure1.jpg)


## Citing AsmMix
If you use AsmMix in your work, please cite:

Liu C, Wu P, Wu X, Zhao X, Chen F, Cheng X, Zhu H, Wang O, Xu M. 
[AsmMix: an efficient haplotype-resolved hybrid de novo genome assembling pipeline.](https://www.frontiersin.org/journals/genetics/articles/10.3389/fgene.2024.1421565/full)
Front Genet. 2024 Jul 26;15:1421565. doi: 10.3389/fgene.2024.1421565. PMID: 39130747; PMCID: PMC11310137.


## Dependencies

parallel

python3

pysam

[minimap2](https://github.com/lh3/minimap2)

[quast](https://github.com/ablab/quast)


## Installation

### Download 
```
git clone https://github.com/BGI-tianjin-dev/AsmMix.git YOUR-INSTALL-DIR
```
No other installation is required.

## Usage 
* Only fasta format of TGS/SLR assembly is acceptable. *

sh asmmix.sh  --tgsasm INPUT_TGS_ASM --slrasm INPUT_SLR_ASM --output OUT_PREFIX --quast quast/quast.py [options...]
  
  required:
  
    --tgsasm     <tgs_assmbly_file>      input TGS assembly.
  
    --slrasm     <slr_assembly_file>     input SLR assembly.
  
    --output     <output_prefix>         output prefix.
  
    --quast      <quast_prefix>          installed quast path.
  
  optional:
  
    --max-length-to-replace  <maxlen args>      for example, --max-length-to-replace 50
  
    --num-thread             <thread args>      for example, --num-thread 32


## Examples

### an example of mixing one haplotype-collapsed TGS long-read assembly with one haplotype-collapsed SLR co-barcoded assembly

If you have a pre-assembled TGS long-read assembly (tgsasm.fasta), and a pre-assembled SLR co-barcoded assembly (slrasm.fasta), then

```
sh asmmix.sh  --tgsasm tgsasm.fasta --slrasm slrasm.fasta --output asmmix --quast quast/quast.py
```

### an example of mixing one haplotype-collapsed TGS long-read assembly with two pseudo-haplotype-resolved SLR co-barcoded assemblies

If you have a pre-assembled TGS long-read assembly (tgsasm.fasta), and two pre-assembled SLR co-barcoded assembly (slrasm.pshap1.fasta && slrasm.pshap2.fasta), then

```
sh asmmix.sh  --tgsasm tgsasm.fasta --slrasm slrasm.pshap1.fasta --output asmmix_pshap1 --quast quast/quast.py

sh asmmix.sh  --tgsasm tgsasm.fasta --slrasm slrasm.pshap2.fasta --output asmmix_pshap2 --quast quast/quast.py
```

### an example of mixing one haplotype-collapsed TGS long-read assembly with two haplotype-resolved SLR co-barcoded assemblies using trio binning

If you have a pre-assembled TGS long-read assembly (tgsasm.fasta), and two pre-assembled SLR co-barcoded assembly (slrasm.mat.fasta && slrasm.pat.fasta), then

```
sh asmmix.sh  --tgsasm tgsasm.fasta --slrasm slrasm.mat.fasta --output asmmix_mat --quast quast/quast.py

sh asmmix.sh  --tgsasm tgsasm.fasta --slrasm slrasm.pat.fasta --output asmmix_pat --quast quast/quast.py
```


## Output
${OUT_PREFIX}.fasta (asmmix.fasta by default)


## Evaluation
[Evaluation](https://github.com/BGI-biotools/AsmMix/tree/main/Evaluation) are scripts for evaluations


## Contact
Any questions, please feel free to ask liuchao3@genomics.cn


## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=AsmMix&type=Date)](https://star-history.com/#BGI-tianjin-dev/AsmMix&Date)

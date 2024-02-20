# AsmMix

AsmMix, which is capable of producing both contiguous and accurate diploid genomes. It first assembles co-barcoded reads to generate accurate haplotype-resolved assemblies that may contain many gaps, while the long-read assembly is contiguous but susceptible to errors. Then those two sets of sequences are compared and integrated into a haplotype-resolved assembly with reduced errors. 


## Citing AsmMix
If you use AsmMix in your work, please cite:
[AsmMix: A pipeline for high-quality diploid de novo assembly](https://www.biorxiv.org/content/10.1101/2021.01.15.426893v1)
Pei Wu, Chao Liu, Ou Wang, Xia Zhao, Fang Chen, Xiaofang Cheng, Hongmei Zhu
doi: https://doi.org/10.1101/2021.01.15.426893

## Dependencies

parallel

python3

pysam

minimap2

## Installation

### Download 
```
git clone https://github.com/BGI-tianjin-dev/AsmMix.git YOUR-INSTALL-DIR
```
No other installation is required.

## Usage 


## Examples
### an example of mixing one haplotype-collapsed TGS long-read assembly with one haplotype-collapsed SLR co-barcoded assembly


### an example of mixing one haplotype-collapsed TGS long-read assembly with two pseudo-haplotype-resolved SLR co-barcoded assemblies


### an example of mixing one haplotype-collapsed TGS long-read assembly with two haplotype-resolved SLR co-barcoded assemblies using trio binning



## Output


## Evaluation
[Evaluation](https://github.com/BGI-biotools/AsmMix/tree/main/Evaluation) are scripts for evaluation

## Contact
Any questions, please feel free to ask liuchao3@genomics.cn

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=AsmMix&type=Date)](https://star-history.com/#BGI-tianjin-dev/AsmMix&Date)



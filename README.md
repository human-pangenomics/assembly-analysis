# Assembly analysis
Assessment of genome assemblies through various evaluation methods

## Motivation
The [CHM13 data and analyses](https://github.com/nanopore-wgs-consortium/CHM13) from the [Telomere-to-Telomere consortium (T2T)](https://sites.google.com/ucsc.edu/t2tworkinggroup) contain BAC analyses for the Canu, Flye, and Shasta assemblies. Here we add QUAST analysis, followed by the table, for the same. 

## QUAST results
### QUAST vs. CHM13 draft v0.7
| | canu.contigs | flye.contigs | shasta.run1 | shasta.run2 |
| --------- | ------ | ------ | ------ | ------ |
| # contigs |  1223 |  472 |  648 |  297 |
| Largest contig |  139909728 |  132009996 |  128776686 |  130803838 |
| Total length |  2991947723 |  2920201070 |  2835274591 |  2823384269 |
| Reference length |  2938464690 |  2938464690 |  2938464690 |  2938464690 |
| GC (%) |  40.92 |  40.96 |  40.92 |  40.9 |
| Reference GC (%) |  40.88 |  40.88 |  40.88 |  40.88 |
| N50 |  77964612 |  70319350 |  56347153 |  58111632 |
| NG50 |  77964612 |  70319350 |  52402611 |  58088067 |
| L50 |  15 |  16 |  17 |  17 |
| LG50 |  15 |  16 |  18 |  18 |
| # misassemblies |  6396 |  3230 |  255 |  187 |
| # misassembled contigs |  875 |  193 |  102 |  78 |
| Misassembled contigs length |  2458710426 |  2440399207 |  1519592488 |  1351075153 |
| # local misassemblies |  1164 |  981 |  179 |  129 |
| # scaffold gap ext. mis. |  0 |  0 |  0 |  0 |
| # scaffold gap loc. mis. |  0 |  1 |  0 |  0 |
| # possible TEs |  160 |  96 |  16 |  14 |
| # unaligned mis. contigs |  73 |  17 |  2 |  0 |
| # unaligned contigs |  168 + 248 part |  8 + 135 part |  0 + 60 part |  0 + 37 part |
| Unaligned length |  30076945 |  14583673 |  548787 |  393547 |
| Genome fraction (%) |  98.391 |  97.392 |  96.557 |  96.149 |
| Duplication ratio |  1.027 |  1.018 |  1.002 |  1.002 |
| # N's per 100 kbp |  0 |  0.07 |  0 |  0 |
| # mismatches per 100 kbp |  77.26 |  74.04 |  20.36 |  15.56 |
| # indels per 100 kbp |  327.08 |  447.97 |  141.3 |  141.25 |
| Largest alignment |  104447985 |  111814657 |  111670942 |  111679369 |
| Total aligned length |  2943726417 |  2894073152 |  2833537204 |  2821352191 |
| NA50 |  47440498 |  46858921 |  40931258 |  47392260 |
| NGA50 |  47440498 |  46546094 |  39828865 |  44539326 |
| LA50 |  21 |  19 |  22 |  19 |
| LGA50 |  21 |  20 |  23 |  20 | 




## Run commands
We ran QUAST using the following command:





# Assembly analysis
Assessment of genome assemblies through various evaluation methods

## Motivation
The [CHM13 data and analyses](https://github.com/nanopore-wgs-consortium/CHM13) from the [Telomere-to-Telomere consortium (T2T)](https://sites.google.com/ucsc.edu/t2tworkinggroup) contain BAC analyses for the Canu, Flye, and Shasta assemblies. Here we add QUAST analysis, followed by the table, for the same. 

## Results
#### QUAST vs. CHM13 draft v0.7
| | canu.contigs | flye.contigs | shasta.run1 | shasta.run2 |
| --------- | ------ | ------ | ------ | ------ |
| # contigs |  1223 |  472 |  648 |  297 |
| Largest contig |  139909728 |  132009996 |  128776686 |  130803838 |
| Total length |  2991947723 |  2920201070 |  2835274591 |  2823384269 |
| N50 |  77964612 |  70319350 |  56347153 |  58111632 |
| NG50 |  77964612 |  70319350 |  52402611 |  58088067 |
| L50 |  15 |  16 |  17 |  17 |
| LG50 |  15 |  16 |  18 |  18 |
| # misassemblies |  6396 |  3230 |  255 |  187 |
| # misassembled contigs |  875 |  193 |  102 |  78 |
| Misassembled contigs length |  2458710426 |  2440399207 |  1519592488 |  1351075153 |
| # local misassemblies |  1164 |  981 |  179 |  129 |
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

## Comments
## Run commands
#### Shasta run 1 - Assembly performed using Shasta commit b48017d3a3b3e7c0d652edba92da9bb88a02e30b

	nohup bin/shastaDynamic --input rel3.fasta --Reads.minReadLength 50000 --MinHash.minBucketSize 5 --MinHash.maxBucketSize 30 --MinHash.minFrequency 5 --Align.minAlignedMarkerCount 400 --Align.minAlignedFraction 0.4 --Assembly.consensusCaller Bayesian:guppy-3.0.5-a --memoryMode filesystem --memoryBacking 2M --assemblyDirectory run1 1>run1.stdout 2>&1 &

#### Shasta run 2 - Assembly performed using Shasta commit 8bb7d52d9f8622a8dee8c3fcfb58e4f4cd1ac9f8

	nohup bin/shastaDynamic --input rel3.fasta --Reads.minReadLength 50000 --MinHash.minBucketSize 10 --MinHash.maxBucketSize 40 --MinHash.minFrequency 10 --MinHash.minHashIterationCount 0 --MinHash.alignmentCandidatesPerRead 10 --Align.minAlignedMarkerCount 400 --Align.minAlignedFraction 0.4 --Align.sameChannelReadAlignment.suppressDeltaThreshold 10 --Assembly.consensusCaller Bayesian:guppy-3.0.5-a --memoryMode filesystem --memoryBacking 2M --assemblyDirectory run2 1>run2.stdout 2>&1 &

#### QUAST - Analysis performed by Marina Haukness (UC Santa Cruz) using quast-5.0.2

	quast-5.0.2/quast-lg.py --threads 128 -r ../chm13.draft_v0.7.fasta --large --min-identity 80 --fragmented Assembly.fasta




---
layout: post
title: Demultiplexing 
subtitle: with Stacks and the dDocent Pipeline
gh-repo: SaraSchaal/AtlanticCodOpenNotebook
gh-badge: [star, fork, follow]
tags: [Bioinformatics Pipeline]
---

**Demultiplexing with Stacks**

To use the dDocent pipeline, demultiplexed files need to be in the format of "Pop1_001.R1.fq.gz" and "Pop1_001.R2.fq.gz" for 
paired end reads. With population number that the sample comes from as the "Pop#" input and then the sample number as a 3 digit 
identifier. 

My population format will be:

|      |             | 
|------|-------------| 
| Pop1 | MassOlive   | 
| Pop2 | MassRed     | 
| Pop3 | MassSpring  | 
| Pop4 | CashesOlive | 
| Pop5 | CashesRed   | 
| Pop6 | IceSWOff    | 
| Pop7 | IceSWNear   | 
| Pop8 | IceNWOff    | 
| Pop9 | IcenWNear   | 

Does it need to be a 3 digit sample code or can I use my original sample naming? Can just link the new pop# and sample
code ID with the samples old ID if this isn't possible. 

Line of code to run stacks:
  * Note from dDocent - do not use -c and -q flags with process_radtags (doesn't explain why)
  
  process_radtags -p /PATHTOFILES -o /PATHFOROUTFILES -b /FILEWITHBARCODES \ --inline_null

--inline_null (because the sequencing facility already demultiplexed to the first level with the index pairs)

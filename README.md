# _Fusarium oxysporum_ f. sp. _cubense_--genomics

Here are the scripts used for genomics study of _Fusarium oxysporum_ f. sp. _cubense_ (Zhang, Y., C.Y. Li, S.W. Liu, C.W. Liu, D. Mostert, H.L. Yu, S. Haridas, K. Webster, M.H. Li, I. Grigoriev, A. Viljoen, G.J. Yi, L.J. Ma (2023) Accessory genes in tropical race 4 contributed to the recent resurgence of the devastating disease of Fusarium wilt of banana. https://www.researchsquare.com/article/rs-3197485/v1)
  
##   Genome assembly

   1. Genome assembly of the PacBio data was performed using Canu v1.8
   
   2. Data from the Illumina libraries were trimmed by removing bases with a quality score below 20 at both ends and discarding trimmed reads with lengths <70 bp (Trimmomatic)

   3. All sequences in the initial assembly were fed into Quiver along with trimmed Illumina sequences to polish the genome assembly

   4. The quality of the assembly was evaluated with GRIDSS and Sniffles; All genomic structural variations were checked and corrected manually

   5. The completeness of all assemblies was confirmed using a BUSCO test employing a fungal database (odb9 version)

##   Genome annotation

   1. Mask low-complexity regions (RepeatMasker)
   2. Protein-coding genes on the repeat-masked genome assembly were predicted at JGI
   3. Functional annotation (including Pfam and Gene Ontology [GO] terms) for the predicted protein-coding genes was performed by InterProScan, following a standard annotation workflow
  
##   Comparative genomics 

    1. Gene family: All proteins from selected F. oxysporum strains were compared by BLAST analysis to evaluate the level of homology. The output from BLAST was processed with OrthoMCL v2.0.9 to group gene families using a cutoff of 1e-5, a minimum aligned sequence length coverage of 50% of the query sequence and an inflation index of 1.5
    2. Construct pan-genome and annotate the pan-genome


   
##   Population genomics

  ####    Phylogenetic framework
    1. Nucleotide sequences of 10 conserved single-copy genes shared by Fusarium species were aligned using ClustalW
    2. Remove regions with poor sequence quality and concatenate alignments into a single supermatrix
    3. Generate maxiumum-likelihood phylogenetic tree using MEGA v10.2.6

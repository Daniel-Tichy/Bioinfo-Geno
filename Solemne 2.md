# Prueba 02 - Bioinformática genómica
___

**Nombre: Daniel Tichy**  
**Fecha:16/05/2016**
&nbsp;

# Classical taxonomy is unable to effectly classify tailed phages further than the family level. 

##  Introduction 
Bacteriophages are the predominant biological entity on the planet, there are more than 10^31 phage particles in the biosphere, 
viral ecologists calculate that its orgins are distant and there are about 10^23 phage infections per second on a global scale,
wich meas that the population is not only large and old but also highly dynamic(1).  
The ongoing sequencing of phage genomes have produced and unprecedented amount of data, which is indispensable for understanding phage biology. but despite of these advances, the taxonomic diversity of phages is just beginning to be assessed.
The International Committee on the Taxonomy of Viruses (ICTV) recognizes several groups of phages, on the basis of shared morphological traits, such as the shape, size, and structure of the virions, with some consideration of other molecular properties.
For example, tailed bacteriophages with double-stranded DNA genomes attain the rank of the order Caudovirales and are divided into 
three main families according to their tail morphology: Siphoviridae (long noncontractile tail), Myoviridae (long contractile tail), 
and Podoviridae (short tail). Within these families, genera are defined by other molecular traits. 
While these families account for more than 60% of Caudovirales, about one-third of all tailed phages remain classified no further 
than the family level(2).
The heart of biological classification is the concept of the species, understood as the smallest group of organisms that can be 
identified robustly.These organisms—through any one of a number of mechanisms—share a common evolutionary fate. 
Importantly, the formation of new lineages of organisms can be equated to the formation of two species from a single ancestral stock.(3)
Today its necesary to divide finely taxonomy for the purpose of understanding bacteriophage biology with the objective of developing 
tools from these. It is clear that placing an organism into a taxonomic “box” has utility only if the box is biologically meaningful. 
In this assay I will argue the infeasibility to classify tailed phages trough a classical (strictly hierarchical) taxonomic paradigm further than the family level given the dynamic of the phage´s genomes evolution.

##  Development 
1.-Classical taxonomic classification requiere orthologus sequences to infer relationships.   
Genome-Based taxonomy is an hypotheses about the evolution of a group of sequences or a gene in particular therefore  requiere orthologus sequences to infer relationships, for example taxonomy based on the 16S rRNA gene (16S) is the most comprehensive and widely used in microbiology today(4) and therefore a taxonomic system based on a single locus analogous to the 16S rDNA in bacteria would be the most straightforward method for classifying phage based on their genomic sequence trough a classical taxonomic paradigm, ergo the formation of new lineages of organisms can be equated to the formation of two species from a single ancestral stock. But phage do not contain a ribosomal sequence that allows them to be classified in different genre and, to date, have not benefited from their own gene-based taxonomic system. Phages even it has been demonstrated that no single gene is found in all phage that can be used as the basis for a classification system. In 2002 Rohwer et al. compared all of the predicted phage encoded proteins (n = 3,981) from 105 completed genomes to each other by using BLASTP. The results are ilustrated in the Figure 1 as a rank abundance curve. There were 21,153 significant hits (E value of <0.1) between the predicted phage proteins. However, no single protein was found in all 105 genomes.    
![Image of Figura 1](https://raw.githubusercontent.com/Daniel-Tichy/Bioinfo-Geno/master/Figura 1S2.jpg)

####Figure 1 
Rank abundance curve showing the number of significant similarities between each predicted phage protein against all other predicted phage proteins, as determined by BLASTP with an E-value cutoff of <0.1.

Therefore taxonomic proposals for this group cannot be based on the analysis of sequence alignments.

2.-Sequence similarity its defined strongly by genetic contact given by host range.  
The genetic diversity of the bacteriophage population is remarkable. In general, the nucleotide sequences of genomes derived from phages with non-overlapping host ranges rarely share sequence similarity, For example, there is no obvious or extensive nucleotide sequence similarity between the published genomes of Streptomyces phages and a collection of mycobacteriophage genomes, even though the Mycobacterium and Streptomyces hosts both are members of the Actinomycetales. And since bacteriophages infecting a common bacterial host are in genetic contact with each other, it is not surprising that they sometimes share common nucleotide sequences.(5)
But at the same time in 2008 Graham F. Hatfull determined that groups that share host range share little or no sequence similarity, as illustrated by nucleotide sequence comparisons of mycobacteriophages and Pseudomonas phages in Figure 2.  

![Image of Figura 2](https://raw.githubusercontent.com/Daniel-Tichy/Bioinfo-Geno/master/Figura 2S2.jpg)

####Figure 2 
Nucleotide sequence relationships among phages infecting common bacterial hosts

In general, phages with different virion morphotypes have different genome organizations and greater sequence diversity; genome architecture may therefore impose constraints on genetic exchange. The evidence in this point is weak and a stadistical analysis could be adde to support the argument. ´

3.-The genomes of bacteriophages are mosaics and their comparison is complex
One of the most striking features of bacteriophage genomes is their apparent mosaic structure; in essence, each genome can be considered as a unique combination of modules that are exchangeable among the population. The size of the modules, their rates of exchange, and the phage genomes carrying them all vary greatly, with phages of different virion morphology, size, and host-range all participants in an orgy of recombination(6) Given the peculiar mosaic structure of these genomes, few informative approaches for comparing whole genomes exist: dot plots diagrams give a mostly qualitative assessment of the similarity/dissimilarity between two or more genomes, and clustering techniques are used to classify genomes. Multiple alignments are conspicuously absent from this scene. Indeed, whole genome aligners interpret lack of similarity between sequences as an indication of rearrangements, insertions, or losses. This behavior makes them ill-prepared to align bacteriophage genomes, where even closely related strains can accomplish the same biological function with highly dissimilar sequences(7). As Graham F. Hatfull illustrated in 2011 in Figure 3. Exchange events occurring in relatively recent evolutionary time can occasionally be seen through whole genome nucleotide comparisons. For example, mycobacteriophages Rosebush and Qyrzula are closely related and share extensive nucleotide sequence similarity. Phage Colbert is a more distant relative sharing similar overall genome organization and many common genes but without a high level of nucleotide sequence similarity. However, a ~1.8 kbp segment of Colbert is closely related to Rosebush (94% nucleotide identity) and was presumably acquired relatively recently from a Rosebush-like phage. Interestingly, the same region in Rosebush is from that in Qyrzula
![Image of Figura 3](https://raw.githubusercontent.com/Daniel-Tichy/Bioinfo-Geno/master/Figura 3S2.jpg)

####Figure 3 
Recent recombination events giving rise to phage genome mosaicism

Therefore an approach based on whole genome comparation is unviable. 

4.-Classical taxonomic approaches can not classify tailed phages yet, phenetics approach can still be used. 
So the genetic diversity observed among bacteriophages remains a major obstacle for their identification and classification. but despite phage divergent and complex evolution, the thorough molecular analysis of a few paradigmatic tailed phages belonging to different morphological classes, such as Siphoviridae SPP1 and λ, Myoviridae T4 and Podoviridae P22 and Φ29, suggested that only a limited number of structural solutions are used in order to produce a functional virion(8) In 2014 Anne Lopes et al. determined that only a limited number of structural solutions are used in order to produce a functional virion. Developing in the process a webserver that automatically identifies proteins of the phage head-neck-tail module and assign phages to the most closely related cluster of phages called Virfam as shown in the Figure 4. 

![Image of Figura 4](https://raw.githubusercontent.com/Daniel-Tichy/Bioinfo-Geno/master/Figura 4S2.jpg)

####Figure 4 
Identification of head-to-tail connection proteins in tailed bacteriophages and representativeness of the different phage Types. (A) Schematic representation of the bioinformatics pipeline used to identify remote homologs of head-to-tail connection proteins. Reference HMM profiles of known head-to-tail connection proteins (Table  1), as well as HMM profiles of each of the 28300 protein sequences contained in the Aclame database, were calculated using PSI-Blast (Step 1). These profiles were compared using HHsearch with a stringent probability threshold of 90%, and proteins detected as related to the reference head-to-tail connection proteins were iteratively used as probes in order to detect further homologs (Step 2). Inter-genes distances were then learned (Step 3) and applied as constraints to faithfully retrieve more remote homologs detected at a lower probability threshold (70%) (Step 4). (B) Components of the four neck Types are represented using the color code defined in Figure  1. Their mean inter-genes distances and standard errors were calculated as illustrated in Step 3 of panel A. (C) Quantitative distribution of the tailed bacteriophages of known morphology and recognized neck Type. Sector color code is the following: white, Siphoviridae of Type 1; light gray, Myoviridae of Type 1; dark gray, Myoviridae of Type 2; hatched, Podoviridae of Type 3; black, Podoviridae of Type 4. Dotted surfaces in Type 1 sectors correspond to phages with incomplete necks, for which one to two canonical components of the neck were not identified.


##  Conclusion 

## References 

1.-Hatfull GF, Hendrix RW. Bacteriophages and their Genomes. Current opinion in virology. 2011;1(4):298-303. 

2.-Glazko G, Makarenkov V, Liu J, Mushegian A. Evolutionary history of bacteriophages with double-stranded DNA genomes. Biol Direct. 2007;2:36.

3.-Lawrence JG, Hatfull GF, Hendrix RW. Imbroglios of Viral Taxonomy: Genetic Exchange and Failings of Phenetic Approaches. Journal of Bacteriology. 2002;184(17):4891-4905. 

4.-Rohwer F, Edwards R. The Phage Proteomic Tree: a Genome-Based Taxonomy for Phage. Journal of Bacteriology. 2002;184(16):4529-4535. doi:10.1128/JB.184.16.4529-4535.2002.

5.-Hatfull GF. Bacteriophage Genomics. Current opinion in microbiology. 2008;11(5):447-453. doi:10.1016/j.mib.2008.09.004.

6.-Hendrix RW, Smith MC, Burns RN, Ford ME, Hatfull GF. Evolutionary relationships among diverse bacteriophages and prophages: all the world's a phage. Proc Natl Acad Sci U S A. 1999;96:2192–2197.

7.-Bérard S, Chateau A, Pompidor N, Guertin P, Bergeron A, Swenson KM. Aligning the unalignable: bacteriophage whole genome alignments. BMC Bioinformatics. 2016;17:30. doi:10.1186/s12859-015-0869-5.

8.-Veesler D, Cambillau C. A common evolutionary origin for tailed-bacteriophage functional modules and bacterial machineries. Microbiol Mol Biol Rev. 2011;75(3):423–433. doi: 10.1128/MMBR.00014-11.

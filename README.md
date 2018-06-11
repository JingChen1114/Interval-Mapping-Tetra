# [Download IntervalMappingTetra](https://github.com/JingChen1114/IntervalMappingTetra/archive/master.zip)

<h2> Contents </h2>

#### [Introduction](https://github.com/JingChen1114/IntervalMappingTetra#-Introduction-)

#### Basix Usage

##### [Usage Instructions](https://github.com/JingChen1114/IntervalMappingTetra#-usage-instructions-)

##### [Input Files](https://github.com/JingChen1114/IntervalMappingTetra#-input-files-)

##### [Output Files](https://github.com/JingChen1114/IntervalMappingTetra#-output-files-)

##### [Example Analysis](https://github.com/JingChen1114/IntervalMappingTetra#-example-analysis-)

##### [Population Simulation](https://github.com/JingChen1114/IntervalMappingTetra#-population-simulation-)

##### [Kmeans Clustering](https://github.com/JingChen1114/IntervalMappingTetra#-kmeans-clustering-)

##### [References](https://github.com/JingChen1114/IntervalMappingTetra#-references-)

<h2> Introduction </h2>

IntervalMappingTetra is a series of related programs that illustrate the interval mapping method (QvMethod and BvMethod) for QTL analysis in autotetraploid species.

<h2> Usage Instructions </h2>

IntervalMappingTetra is supplied as a set of Fortran 90 (.for) source files in the folder BvMethod_FortranSource for BvMethod and Fortran 90 (.for) source files in the folder QvMethod_FortranSource for QvMethod. In folder BvMethod_FortranSource, source files includes:

<b> main.for </b>
The main fortran program for carrying our QTL mapping in autotetraploids by assuming bivalent pairing during meiosis

<b> ParentQTLGenotype.for </b>
Subroutine for working out all the possible parental genotypes on QTL for two parents by assuming parent 1 (fqtype) taking higher trait phenotype value

<b> posszygote.for </b>
Subroutine for calculating the conditional probability of possible chromosome configurations of interval and QTL genotypes for a offspring individual, given all the marker phenotypes on the chromosome of this individual and the parental marker genotypes

<b> pairing.for </b>
Subroutine for assigning a specific bivalent pairing for parent

<b> possgamete.for </b>
Subroutine for working out the two-locus gametes mode under bivalent pairing

<b> proba_g_o.for </b>
Subroutine for calculating the probability distribution of two-locus gametes

<b> proba_g_o_multilocus.for </b>
Subroutine for carrying out multilocus linkage analysis by using hidden Markov chain model under bivalent paring

<b> ge_interval.for </b>
Subroutine used by proba_g_o_multilocus.for to carry out multilocus linkage analysis

<b> tra_matrix.for </b>
Subroutine for calculating probability transition matrix in the hidden Markov chain model

<b> check_ph.for </b>
Subroutine used by proba_g_o_multilocus.for to carry out multilocus linkage analysis

<b> proba_q_g.for </b>
Subroutine for calculating the QTL genotype distribution given marker genotype configuration

<b> EMalgorithm.for </b>
Subroutine for carrying out EM algorithm to obtain the MLE of genotypic value and its corresponding likelihood and LOD score for a pupative QTL

<b> QTLdistribution.for </b>
Subroutine for calculating one locus (QTL here) genotype distribution in an outbreeding population with bivalent pairing

<b> check.for </b>
Subroutine for selecting parental QTL genotypes



In the folder QvMethod_FortranSource, source files includes:

<b> main.for </b>
The main fortran program for carrying our QTL mapping in autotetraploids by assuming quadrivalent pairing during meiosis

<b> ParentQTLGenotype.for </b>
Subroutine for working out all the possible parental genotypes on QTL for two parents by assuming parent 1 (fqtype) taking higher trait phenotype value

<b> Pr_ChrConfig_Markers.for </b>
Subroutine for calculating conditional probability of the chromosome configuration of a marker interval for a offspring individual, given all the marker phenotype on the chromosome of an offspring individual and parental marker genotypes

<b> possgamete.for </b>
Subroutine for working out two-locus gamete modes under quadrivalent pairing

<b> proba_g_o.for </b>
Subroutine for calculating the probability distribution of two-locus gametes under quadrivalent pairing

<b> proba_g_o_multilocus.for </b>
Subroutine for carrying out multilocus linkage analysis by using hidden Markov chain model under quadrivalent paring

<b> ge_interval.for </b>
Subroutine used by proba_g_o_multilocus.for to carry out multilocus linkage analysis

<b> tra_matrix.for </b>
Subroutine for calculating probability transition matrix in the hidden Markov chain model

<b> check_ph.for </b>
Subroutine used by proba_g_o_multilocus.for to carry out multilocus linkage analysis

<b> Pr_QTL_ChrConfig.for </b>
Subroutine for calculating the conditional probability of the QTL genotypes for an offspring individual, given the chromosome configuration and parental QTL genotypes under quadrivalent pairing

<b> proba_q_q.for </b>
Subroutine for calculating the QTL genotypes distribution given flanking marker configuration

<b> EMalgorithm.for </b>
Subroutine for carrying out EM algorithm to obtain the MLE of genotypic value and its corresponding likelihood and LOD score for a pupative QTL

<b> QTLdistribution.for </b>
Subroutine for calculating one locus (QTL here) genotype distribution in an outbreeding population with quadrivalent pairing

<b> check.for </b>
Subroutine for selecting parental QTL genotypes

To use the program an Intel Fortran Compiler is required. The programs can be be compiled and built under Linux or Windows operating systems.
An example is given here for how to compile, build and run the programs using the Microsoft Visual Studio IDE in Windows.

In Microsoft Developer Studio, open an empty project, give it a name, for example "MyQvMethodAnalysis" and save to the desired location. Add all 14 *.for files as source files in the QvMethod_FortranSource folder to the project.
Build the solution from the Build menu and check there are no errors in the output window. 

<h2> Input files </h2>

<b> info_mapping.txt </b>
A input file containing data of a segregation population for QTL mapping analysis. A single header line contains the number of individuals in the population and the number of marker loci in the linkage group.  Paternal and maternal genotypes (i.e. 1 and 2 are used to indicate two difference alleles) on each marker locus are given on separate lines.  Coefficient of double reduction at the marker loci and recombination frequencies between markers (marker i and i-1) are given out in a single line each. Note the first value on the line for recombination frequency is set to be zero. Marker phenotypes of offspring on each marker locus are given on separate lines individual by individual. Finally the trait phenotype score for each individual is given on separate lines. Two example input files are provided in the folder "RealDataAanalysis_Bv" and "RealDataAnalysis_Qv".

<b> kmeans.txt </b>
A input file containing intial values setting for EM algorithm, which is generated by programs in folder "K_Means_Bv" or "K_means_Qv".

<h2> Output files </h2>

<b> MappingOutcome1.txt </b>
Contains results of estimates along the chromsome, including parental QTL genotypes, BIC, likelihood, genetic distance, estimated genotypic value and the residual error.

<b> MappingOutcome2.txt </b>
Contains the MLE of parenal QTL genotypes, BIC, likelihood, genetic distance, genotypic value and residual error. 

<h2> Example analysis </h2>

<h2> Population simulation </h2>
Two sets of Fortran 90 source files are provided for simulation of a segregating population under either bivalent or quadrivalent settings for chromosome pairing in an autotetraploid meiosis.
To simulate offspring populations under either setting, the programs need to be compiled and built as a single fortran project with  
*.for files as source files in the folder of Simulation_Bv for bivalent pairing or Simulation_Qv for quadrivalent pairing.
The input file "data_in

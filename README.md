# [Download IntervalMappingTetra](https://github.com/JingChen1114/IntervalMappingTetra/archive/master.zip)

<h2> Contents </h2>

#### [Introduction](https://github.com/JingChen1114/IntervalMappingTetra#-Introduction-)

#### Basix Usage

##### [Usage Instructions](https://github.com/JingChen1114/IntervalMappingTetra#-usage-instructions-)

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
Subroutine for carrying out multilocus linkage analysis using hidden Markov chain model

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



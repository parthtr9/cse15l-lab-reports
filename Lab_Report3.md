# **Part 1**
## Bugs

1. A failure-inducing input:

Junit test:

```
@Test
public void testReversed() {
   int[] input1 = {1,2,3};
   assertArrayEquals(new int[]{3,2,1}, ArrayExamples.reversed(input1));
  }
```

2. An input that doesn't induce a failure:
   
Junit test:

```
@Test
  public void testReversed1() {
    int[] input1 = {1,2,1};
    assertArrayEquals(new int[]{1,2,1}, ArrayExamples.reversed(input1));
  }
```

3.The symptom:
<img width="892" alt="Screenshot 2024-02-13 at 4 27 08 PM" src="https://github.com/parthtr9/cse15l-lab-reports/assets/154461332/8129d93d-dcb7-4f4e-9a21-4debe0cc6458">

4.

Before:
```
    static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

After:
```
     static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

The issue was that the newArray was never correctly updated and would return zeros in the entire array. 
This occurred due to incorrectly placing the reversed values to the original array.
So correctly changing arr with newArray and vice versa the issue was resolved.

---
---

# **Part 2**
## **Find**

1. List just directories:
> It is useful for finding just the directories in a workspace.

For `/technical`
`find /Users/parth/Desktop/docsearch/technical -type d`
```
parth@Parths-MacBook-Air technical % pwd
/Users/parth/Desktop/docsearch/technical
parth@Parths-MacBook-Air technical % find /Users/parth/Desktop/docsearch/technical -type d
/Users/parth/Desktop/docsearch/technical
/Users/parth/Desktop/docsearch/technical/government
/Users/parth/Desktop/docsearch/technical/government/About_LSC
/Users/parth/Desktop/docsearch/technical/government/Env_Prot_Agen
/Users/parth/Desktop/docsearch/technical/government/Alcohol_Problems
/Users/parth/Desktop/docsearch/technical/government/Gen_Account_Office
/Users/parth/Desktop/docsearch/technical/government/Post_Rate_Comm
/Users/parth/Desktop/docsearch/technical/government/Media
/Users/parth/Desktop/docsearch/technical/plos
/Users/parth/Desktop/docsearch/technical/biomed
/Users/parth/Desktop/docsearch/technical/911report
```
For `/technical/government`
`find /Users/parth/Desktop/docsearch/technical/government -type d`
```
parth@Parths-MacBook-Air technical % pwd 
/Users/parth/Desktop/docsearch/technical
parth@Parths-MacBook-Air technical % cd government 
parth@Parths-MacBook-Air government % pwd
/Users/parth/Desktop/docsearch/technical/government
parth@Parths-MacBook-Air government % find /Users/parth/Desktop/docsearch/
technical/government -type d
/Users/parth/Desktop/docsearch/technical/government
/Users/parth/Desktop/docsearch/technical/government/About_LSC
/Users/parth/Desktop/docsearch/technical/government/Env_Prot_Agen
/Users/parth/Desktop/docsearch/technical/government/Alcohol_Problems
/Users/parth/Desktop/docsearch/technical/government/Gen_Account_Office
/Users/parth/Desktop/docsearch/technical/government/Post_Rate_Comm
/Users/parth/Desktop/docsearch/technical/government/Media
```
---

2. Find by content:
> It is useful for finding files with a certain word in them. 

For `/technical/911report` searching for carry-on:
`find /Users/parth/Desktop/docsearch/technical/911report -name "*txt" -exec grep -Hi carry-on {} \;`
```
parth@Parths-MacBook-Air technical % cd 911report 
parth@Parths-MacBook-Air 911report % pwd 
parth@Parths-MacBook-Air 911report % find /Users/parth/Desktop/docsearch/
technical/911report -name "*txt" -exec grep -Hi carry-on {} \;
/Users/parth/Desktop/docsearch/technical/911report/chapter-13.2.txt:                consequence would have been the screening of their carry-on and checked bags for
/Users/parth/Desktop/docsearch/technical/911report/chapter-13.3.txt:                secondary screening of their carry-on belongings, and checked baggage. See FAA
/Users/parth/Desktop/docsearch/technical/911report/chapter-3.txt:                extraordinary screening of their carry-on baggage as had been the case before the
/Users/parth/Desktop/docsearch/technical/911report/chapter-3.txt:                and "random" hand searches of carry-on luggage at checkpoints had been replaced by
/Users/parth/Desktop/docsearch/technical/911report/chapter-3.txt:                Therefore, secondary screening of individuals and their carry-on bags to identify
/Users/parth/Desktop/docsearch/technical/911report/chapter-1.txt:    In passing through these checkpoints, each of the hijackers would have been screened by a walk-through metal detector calibrated to detect items with at least the metal content of a .22-caliber handgun. Anyone who might have set off that detector would have been screened with a hand wand-a procedure requiring the screener to identify the metal item or items that caused the alarm. In addition, an X-ray machine would have screened the hijackers' carry-on belongings. The screening was in place to identify and confiscate weapons and other items prohibited from being carried onto a commercial flight.
/Users/parth/Desktop/docsearch/technical/911report/chapter-1.txt:    Mihdhar and Moqed placed their carry-on bags on the belt of the X-ray machine and proceeded through the first metal detector. Both set off the alarm, and they were directed to a second metal detector. Mihdhar did not trigger the alarm and was permitted through the checkpoint. After Moqed set it off, a screener wanded him. He passed this inspection.
/Users/parth/Desktop/docsearch/technical/911report/chapter-1.txt:    About 20 minutes later, at 7:35, another passenger for Flight 77, Hani Hanjour, placed two carry-on bags on the X-ray belt in the Main Terminal's west checkpoint, and proceeded, without alarm, through the metal detector. A short time later, Nawaf and Salem al Hazmi entered the same checkpoint. Salem al Hazmi cleared the metal detector and was permitted through; Nawaf al Hazmi set off the alarms for both the first and second metal detectors and was then hand-wanded before being passed. In addition, his over-the-shoulder carry-on bag was swiped by an explosive trace detector and then passed. The video footage indicates that he was carrying an unidentified item in his back pocket, clipped to its rim.
/Users/parth/Desktop/docsearch/technical/911report/chapter-5.txt:                officials searched his carry-on bag and even opened the toiletries kit, but just
/Users/parth/Desktop/docsearch/technical/911report/chapter-5.txt:                carry-on. None of the flight attendants took notice.
/Users/parth/Desktop/docsearch/technical/911report/chapter-12.txt:                carry-on bags. TheTSA is dealing with the kind of screening issues that are being
/Users/parth/Desktop/docsearch/technical/911report/chapter-12.txt:                (1) screening people for explosives, not just their carry-on bags, and (2) improving

```

For `/technical/plos` searching for chromosome:
`find /Users/parth/Desktop/docsearch/technical/plos -name "*txt" -exec grep -Hi chromosome {} \;`
```
parth@Parths-MacBook-Air technical % cd plos
parth@Parths-MacBook-Air plos % pwd
/Users/parth/Desktop/docsearch/technical/plos
parth@Parths-MacBook-Air plos % find /Users/parth/Desktop/docsearch/
technical/plos -name "*txt" -exec grep -Hi chromosome {} \;
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020347.txt:        portions of the chromosomes are associated with the transgressive variation of interest.
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020347.txt:        genes or, more correctly, quantitative trait loci (QTLs) map along the chromosomes.
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020347.txt:        chromosome segment substitution lines, called introgression lines when the donor is a wild
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020420.txt:        Surprisingly, these genes map to very different areas of the chromosomes than do genes that
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030021.txt:        which the sex of offspring is set by a sex chromosome or an autosomal gene, and
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030021.txt:        the GSD systems many different mechanisms have been uncovered. Dual sex chromosome systems,
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030021.txt:        systems set by the ratio of the number of X chromosomes to sets of autosomes (X:A). There
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030021.txt:        Y chromosome inhibits this autoregulation [15]. As a result, males cannot make functional
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        considering its basic function of inheritance, in which all parts of all chromosomes must
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        chromosome that stimulate the action of proteins that bring about recombination (Eggleston
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        chromosomes have local recombination hotspots where crossing over is much more likely to
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        occur than in other places on the chromosome. Recombination hotspots are local regions of
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        chromosomes, on the order of one or two thousand base pairs of DNA (or less—their length is
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        eukaryotes are initiated by the cleavage of single chromosomes, called “double-strand
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        their possible effect on the patterns of DNA sequence variation along human chromosomes and
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        a chromosome, are aligned, they reveal the location and distribution of variation at
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        eight haplotypes for a series of SNPs found over a region of a chromosome. Given diverse
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        recombinant haplotypes and thus also favoring those chromosomes that happen to have a high
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        segregation of chromosomes during meiosis (Paques and Haber 1999; Lichten 2001; Hunter
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        chromosome segregation, but they occur after the formation of the SC. Both of these species
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        Recombination during meiosis seems to be required for proper chromosome segregation;
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020190.txt:        recombination machinery has been partly co-opted for chromosome alignment in some
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020068.txt:        location of genes in the ancestral chromosome) and selection acting on the combined fitness
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020241.txt:        Apcs , however, is located in a region near the tip of mouse Chromosome 1
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020241.txt:        gene of interest), carrying the same 129 region on Chromosome 1, but expressing 
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020043.txt:        divisions) whereby one diploid nucleus (with two copies of each chromosome) becomes four
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020043.txt:        genetically different haploid nuclei (each with one copy of each chromosome). Only one of
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020043.txt:        bodies fuse together into a triploid cell (with three copies of each chromosome), and this
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020043.txt:        copies of each chromosome). This pentaploid cell then proliferates to form the bacteriome
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020043.txt:        are enriched for chromosome regions 
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020043.txt:        If there were no crossing over between homologous chromosomes during meiosis, then the
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020043.txt:        first meiotic division would consistently separate the chromosomes derived from the
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020043.txt:        mother's mother from the chromosomes derived from the mother's father, producing two cells
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020043.txt:        mosaic of related and unrelated chromosome regions between the products of the first
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020043.txt:          chromosomes they inherited from their mother, and all of a male's sperm are identical to
/Users/parth/Desktop/docsearch/technical/plos/pmed.0020212.txt:        region on Chromosome 2 was stringently significant and several additional regions neared
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        proper number of chromosomes. The dividing cell closely monitors that chromosomes are
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        the chromosomes (now comprising two chromatids) align at the center of the cell, and are
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        centromere, a characteristic constriction carried by each chromosome. The spindle, which is
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        chromosomes are gathered together at each pole of the cell, which can then divide. Cohesion
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        between chromosome copies, which keeps the chromatids together until just the right time,
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        Chromosome cohesion is established during S phase (when the chromosomes are replicated)
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        the result of the improper dissolution of chromosome cohesion [2]. Finally, mutation of a
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        factor required to load cohesin—the protein complex responsible for chromosome
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        cohesion—onto chromosomes appears to cause Cornelia de Lange syndrome, a clinically
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        chromosomes, such that each chromosome becomes attached to the two poles of the spindle
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        [6]. Second, it prevents the splitting of chromosomes until all bipolar attachments are
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        microtubules, which pull the chromosomes to opposite spindle poles; this force is not
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        exerted along the chromosome arms, which means that cohesion at centromeres and along arms
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        is functionally distinct. Third, cohesion along chromosome arms may be essential for proper
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        chromosome condensation [7,8], although the function of cohesion at chromosome arms is
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        and Scc3 (SA2). The Smc (structural maintenance of chromosomes) proteins form
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        centromere and the nearby pericentric domain, and (2) cohesin associated with chromosome
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        on meiotic chromosomes for 
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        pericentric cohesion are important for chromosome dynamics, but the functional differences
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        apparently sufficient to allow dissociation from chromosome arms, which occurs during
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        therefore dissociation from chromosomes is prevented—by proteins known as shugoshins
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        chromosomes are ready to separate [35]. Vertebrate shugoshin has been shown to have a
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        acting as part of a spindle checkpoint that monitors whether chromosomes are properly
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        mechanisms to dissociate cohesin from chromosomes, although it is interesting to speculate
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        that this could be related to different functions of cohesin at chromosome arms versus
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        pericentric domains. For instance, cohesin in chromosome arms may help to organize or
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        condense chromosomes, whereas cohesin at centromeres may be more directly involved in
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        chromosome bi-orientation at the spindle and segregation. These functions may be important
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        results in chromosome missegregation and cell death [13]. Cohesin is found at the
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        boundaries of the HMR locus, the right telomere of Chromosome III, and the RDN1 array, all
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        particularly important for cohesin association with chromosome arms [43]. The chromatin
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        chromosome arms and centric regions will turn out to be related to different mechanisms for
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        While one of the primary roles for chromosome cohesion in bi-orientation and mitotic
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        chromosome segregation is well-established, the complexities of the regulation of cohesion
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        are still being discovered. Cohesin may be involved in multiple ways in chromosome
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030094.txt:        dynamics. Future studies focusing on the differences between cohesion at chromosome arms
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020133.txt:        pathways have essential roles in development, chromosome structure, and virus resistance.
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020133.txt:        proteins (histones), thus generating condensed, transcriptionally silent chromosome regions
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020133.txt:        essential for normal chromosome segregation. The RNAi-dependent heterochromatin pathway has
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020133.txt:        general means for creating condensed, silent chromosome domains.
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020116.txt:        considerably by growth in vitro with retention of normal chromosome structure and number,
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010051.txt:        showed a Robertsonian (i.e., of the whole arms) translocation of Chromosome 14 and 21
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010051.txt:        involving the long arm of Chromosome 21. Except for mild adrenal insufficiency noted on an
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030062.txt:        action, not by structural chromosome differences or failure of meiosis.
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0030062.txt:        that has two unlike sex chromosomes).
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020064.txt:        compound, had been linked to a locus on human Chromosome 5p15. Reasoning that this
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020064.txt:        resembled GPCRs on Chromosome 5p15. ‘That was how we found T2R1, the first bitter receptor,
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020148.txt:        desired mutation on one of their chromosomes. ‘It is then a matter of identifying these
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020206.txt:        that replication-dependent chromosome breakages also play a significant role in generating
/Users/parth/Desktop/docsearch/technical/plos/journal.pbio.0020206.txt:        CDYL gene to Y chromosome (forming 
```
---

3.Find files by type:
> It is useful for finding files with certain type in the workspace.

For `/technical/911reports`:
`find /Users/parth/Desktop/docsearch/technical/911report -type f`
```
parth@Parths-MacBook-Air technical % pwd
/Users/parth/Desktop/docsearch/technical
parth@Parths-MacBook-Air technical % cd 911report 
parth@Parths-MacBook-Air 911report % pwd
/Users/parth/Desktop/docsearch/technical/911report
parth@Parths-MacBook-Air 911report % find /Users/parth/Desktop/docsearch/
technical/911report -type f
/Users/parth/Desktop/docsearch/technical/911report/chapter-13.4.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-13.5.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-13.1.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-13.2.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-13.3.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-3.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-2.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-1.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-5.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-6.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-7.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-9.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-8.txt
/Users/parth/Desktop/docsearch/technical/911report/preface.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-12.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-10.txt
/Users/parth/Desktop/docsearch/technical/911report/chapter-11.txt
```

For `/technical/government/alcohol_problems`:
`find /Users/parth/Desktop/docsearch/technical/government/alcohol_problems -type f`
```
parth@Parths-MacBook-Air technical % pwd 
/Users/parth/Desktop/docsearch/technical
parth@Parths-MacBook-Air technical % cd government
parth@Parths-MacBook-Air government % cd alcohol_problems
parth@Parths-MacBook-Air alcohol_problems % pwd
/Users/parth/Desktop/docsearch/technical/government/alcohol_problems
parth@Parths-MacBook-Air alcohol_problems % find /Users/parth/Desktop/docsearch/
technical/government/alcohol_problems -type f
/Users/parth/Desktop/docsearch/technical/government/alcohol_problems/Session2-PDF.txt
/Users/parth/Desktop/docsearch/technical/government/alcohol_problems/Session3-PDF.txt
/Users/parth/Desktop/docsearch/technical/government/alcohol_problems/DraftRecom-PDF.txt
/Users/parth/Desktop/docsearch/technical/government/alcohol_problems/Session4-PDF.txt
```
---

4.Find a single file by approximate name:
> It is useful for finding files with reoccuring names or finding files that you do not remember the full name of.

For `/techinical/biomed` finding all txt files starting with cc:
`find /Users/parth/Desktop/docsearch/technical/biomed -iname "cc*txt"`
```
parth@Parths-MacBook-Air technical % pwd
/Users/parth/Desktop/docsearch/technical
parth@Parths-MacBook-Air technical % cd biomed 
parth@Parths-MacBook-Air biomed % pwd
/Users/parth/Desktop/docsearch/technical/biomed
parth@Parths-MacBook-Air biomed % find /Users/parth/Desktop/docsearch/
technical/biomed -iname "cc*txt"
/Users/parth/Desktop/docsearch/technical/biomed/cc991.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc4.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc367.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc3.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc2190.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1843.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1856.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc105.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1498.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1538.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1882.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc300.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1529.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc103.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc303.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1477.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1852.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc713.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1476.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc2172.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc2358.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc2167.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc2171.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc2160.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1044.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1497.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1495.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc350.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc973.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc1547.txt
/Users/parth/Desktop/docsearch/technical/biomed/cc343.txt
```

For `/technical/plos` finding all txt files starting with pmed.001
`find /Users/parth/Desktop/docsearch/technical/plos -iname "pmed*001*txt"`
```
parth@Parths-MacBook-Air technical % pwd
/Users/parth/Desktop/docsearch/technical
parth@Parths-MacBook-Air technical % cd plos 
parth@Parths-MacBook-Air plos % pwd
/Users/parth/Desktop/docsearch/technical/plos
parth@Parths-MacBook-Air plos % find /Users/parth/Desktop/docsearch/
technical/plos -iname "pmed*001*txt"
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010039.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010010.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010013.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010028.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010029.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010066.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010067.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010071.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010058.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010070.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010064.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010048.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010060.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010061.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010049.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0020015.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0020017.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010062.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0020016.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010047.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010046.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010052.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0020018.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010050.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010051.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010045.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0020019.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010069.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010041.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010068.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010056.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010042.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010030.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010024.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010025.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010026.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010022.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010036.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010023.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010021.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010034.txt
/Users/parth/Desktop/docsearch/technical/plos/pmed.0010008.txt

```

---
---
Sources used:
[Redhat](https://www.redhat.com/sysadmin/linux-find-command),
[tecmint](https://www.tecmint.com/35-practical-examples-of-linux-find-command/)







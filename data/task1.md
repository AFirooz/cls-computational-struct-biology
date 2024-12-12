All files
All files and results are available on GitHub at https://github.com/AFirooz/submodule-modeller/tree/main

The coding files are under the "src" directory and result files are under "data".



Detailed steps, scripts, and parameters
Scripts and parameters are available online on Github if you prefer to see it locally, run "git clone https://github.com/AFirooz/submodule-modeller.git"



Step 1 - Build Profile
I used these extra resources to help:
https://bionerdnotes.wordpress.com/2020/03/25/how-to-use-modeller-for-homology-based-modelling/
https://bionerdnotes.wordpress.com/2020/04/01/multi-chain-modelling-in-modeller/


the latest "pdb_95.pir.gz" was downloaded from https://salilab.org/modeller/downloads
the sequence pir file was then parsed into a SequenceDB and saved into a binary file
created a profile using BLOSUM62 similarity matrix with gap penalties and matrix offset. Iterating only once.


The resulted profile:

# Number of sequences:   33

# Length of profile :  759

# N_PROF_ITERATIONS :   1

# GAP_PENALTIES_1D  :  -500.0  -50.0

# MATRIX_OFFSET   : -450.0

# RR_FILE      : ${LIB}/blosum62.sim.mat

------------------------------------------------------------------------------------------------------------------------

H1  H2*   H3                 H4  H5  H6  H7  H8  H9  H10* H11*  H12*    comment

   code[:4]+chain[4:]                                len  %    e-value  * most important columns

------------------------------------------------------------------------------------------------------------------------

1   Target_Assign_3 S              0   759  1   759  0   0   0   0.   0.0   

*2  3l56B  X                  1   205  541  745  1   205  205  98.   0.0   

3   5ef9A  X                  1   168  325  488  4   165  162  38.   0.0    any percentage > 25% is good

4   4q46A  X                  1   164  325  482  7   163  157  39.   0.0     

~5  4uafE  X                  1   72  687  758  1   72  72  97.   0.0    even though percentage>25%, the len<100. Not good.

6   5m3hC  X                  1   730  1   742  3   730  728  68.   0.0     

*7  3kc6A  X                  1   198  540  739  1   198  198  97.   0.0      

8   4wrtC  X                  1   250  1   247  4   250  247  40.   0.0       

~9  3a1gB  X                  1   38  1   35  4   38  35  94.   0.18E-10  lower e-value is the most important 

*10  6qpfC  X                  1   727  1   756  1   727  727  97.   0.0      

~11  2jdqD  X                  1   63  688  756  1   63  63  97.   0.0    low sequence length

12  4u6oA  X                  1   166  318  483  1   166  166  95.   0.0   

13  4u6oB  X                  1   156  320  483  1   156  156  95.   0.0   

14  2vy8A  X                  1   152  538  693  2   152  151  95.   0.0   

15  6qnwC  X                  1   724  1   756  1   724  724  95.   0.0   

16  6qnwL  X                  1   709  1   756  1   709  709  95.   0.0   

17  5d98C  X                  1   762  5   755  9   762  729  24.   0.0   

18  5d9aC  X                  1   754  5   755  9   754  725  24.   0.0   

19  6euyB  X                  1   267  252  532  1   267  267  94.   0.0   

20  6euxA  X                  1   225  257  518  2   225  224  38.   0.0   

21  6euvA  X                  1   277  252  532  1   277  277  94.   0.0   

*22  6euwA  X                  1   156  319  482  1   156  156  98.   0.0   

23  5eg7A  X                  1   161  319  483  1   161  161  95.   0.0   

24  6evjC  X                  1   748  1   749  2   748  744  69.   0.0   

25  5wl0A  X                  1   482  252  737  1   482  482  94.   0.0   

26  4eqkA  X                  1   163  321  483  1   163  163  92.   0.0   

27  3r2vA  X                  1   192  541  738  1   192  192  93.   0.0   

*28  5fmmA  X                  1   425  251  675  1   425  425  98.   0.0   

29  5fmzF  X                  1   703  1   736  3   703  698  38.   0.0   

30  7xmeB  X                  1   154  321  482  1   154  154  92.   0.0   

!31  7nfqA  X                  1   279  252  532  1   279  279  97.   0.0   

32  7z42C  X                  1   718  1   736  3   718  712  38.   0.0   

33  7z42F  X                  1   728  1   736  3   728  722  38.   0.0   



~ Unchosen templates.

* Chosen templates.

! causes some exception





Step 2 - 5 templates were selected
based on the sequence length, percentage of alignment, and the e-value. From there I did extra alignments and energy calculation to find out which is better to choose.

I created this ID Tree and Dendrogram:



Sequence identity comparison (ID_TABLE):



  Diagonal    ... number of residues;

  Upper triangle ... number of identical residues;

  Lower triangle ... % sequence identity, id/min(length).



     3l56B @23kc6A @26qpfC @36euwA @15fmmA @2

3l56B @2   205   187   128    2   130

3kc6A @2    94   198   127    2   129

6qpfC @3    62   64   727    2   150

6euwA @1    1    1    1   156    2

5fmmA @2    63   65   35    1   425





Weighted pair-group average clustering based on a distance matrix:





                                .--- 3l56B @2.3   6.0000

                                |

                       .--------------------- 3kc6A @2.0  36.0000

                       |

                  .------------------------------ 5fmmA @2.4  51.0000

                  |

    .---------------------------------------------------------- 6qpfC @3.6  99.0000

    |

   .------------------------------------------------------------ 6euwA @1.0



   +----+----+----+----+----+----+----+----+----+----+----+----+

  102.7200  85.9800  69.2400  52.5000  35.7600  19.0200  2.2800

     94.3500  77.6100  60.8700  44.1300  27.3900  10.6500



From the (above) ID Table, we see:



- **6qpfC** has the most residues (727), indicating it might cover more of the target.

- **6euwA** has the fewest residues (156), suggesting it may represent a smaller fragment or region.

- **3l56B** vs. **3kc6A**: 94% sequence identity, indicating very high similarity.

- **3l56B** vs. **6qpfC**: 62%.

- **3kc6A** vs. **6qpfC**: 64%.

- **6euwA** has essentially no significant sequence similarity to the others (all 1%).



Looking at the Dendrogram:



- **3l56B** and **3kc6A** are the closest, forming the first branch (6.0 distance), confirming their similarity.

- **5fmmA** joins next (51.0 distance), showing moderate similarity to **3l56B** and **3kc6A**.

- **6qpfC** is more distant (99.0 distance), indicating it is structurally diverse.

- **6euwA** is the most divergent and joins the tree last.





Template Selection:

- **3kc6A** over **3l56B** and **5fmmA**, as it has lower crystallographic resolution. Although **5fmmA**, can be a good secondary structural features align.

- **6qpfC** has the highest residue count (727) and could provide coverage for larger regions. But it's more distant structurally (distance 99), so it might not be ideal as a primary template but can complement the main one. So we choose this over **6euwA**.



Step 3 - Perform 2d Alignment
where all identical positions are marked with a "*":

 _aln.pos     10    20    30    40    50    60

3kc6A   -----------------------------------------N-------------------------- 

Assign_3 MERIKELRDLMSQPRTREILTKTTVDHMAIIKKYTSGRQEKNPALRMKWMMAMKYPITADKRIMEMIP 

 _consrvd                     *



 _aln.p  70    80    90    100    110    120    130

3kc6A   ----------------GPESVLVN--TYQWIIRNWET------------------------------- 

Assign_3 ERNEQGQTLWSKTNDAGSDRVMVSPLAVTWWNRNGPTTSTVHYPKVYKTYFEKVERLKHGTFGPVHFR 

 _consrvd         *  * *   * ** *



 _aln.pos 140    150    160    170    180    190    200

3kc6A   --VKI---------------QWSQD--------------------------------------PTMLY 

Assign_3 NQVKIRRRVDINPGHADLSAKEAQDVIMEVVFPNEVGARILTSESQLTITREKKEELHDCKIAPLMVA 

 _consrvd  ***         **                   * *



 _aln.pos  210    220    230    240    250    260    270

3kc6A   NKME--------------------FE------------------------------------------ 

Assign_3 YMLERELVRKTRFLPVAGGTSSVYIEVLHLTQGTCWEQMYTPGGEVRNDDVDQSLIIAARNIVRRATV 

 _consrvd  *           *



 _aln.pos   280    290    300    310    320    330    340

3kc6A   ---PFQSLV--------------------P---------KAARG-------QYSGFV----------- 

Assign_3 SADPLASLLEMCHSTQIGGVRMVDILRQNPTEEQAVDICKAALGLRISSSFSFGGFTFKRTSGSSVKK 

 _consrvd  * **           *     *** *     **



 _aln.pos    350    360    370    380    390    400

3kc6A   --------------------------------------RTLFQQMR---------------------D 

Assign_3 EEEVLTGNLQTLKIRIHEGYEEFTMVGRRATAILRKATRRLIQLIVSGRDEQSIAEAVIVAMVFSQED 

 _consrvd                    * * *            *



 _aln.p 410    420    430    440    450    460    470

3kc6A   -----------------------------------VL------------------------------- 

Assign_3 CMIKAVRGDLNFVNRANQRLNPMHQLLRHFQKDAKVLFQNWGIEPIDNVMGMIGILPDMTPSTEVSLR 

 _consrvd                  **



 _aln.pos 480    490    500    510    520    530    540

3kc6A   -------G---------------------------------------------TF------------- 

Assign_3 GVRVSKMGVDEYSSTERVVVSIDRFLRVRDQRGNVLLSPEEVSETQGTEKLTITYSSSMMWEINGPES 

 _consrvd    *                       *



 _aln.pos  550    560    570    580    590    600    610

3kc6A   ---DTVQII---------------KLL-------PFAAAPPKQSR----------------------- 

Assign_3 VLVNTYQWIIRNWETVKIQWSQDPTMLYNKMEFEPFQSLVPKAARGQYSGFVRTLFQQMRDVLGTFDT 

 _consrvd   * * *         *    **  ** *



 _aln.pos   620    630    640    650    660    670    680

3kc6A   ------------------MQFSSLTVNVR--GMRILVRGNSPVFNYNKATKRLTVLGKDAGALTEDPD 

Assign_3 VQIIKLLPFAAAPPEQSKMQFSSLTVNVRGSGMRILVRGNSPVFNYNKATKRLTILGKDAGALTEDPD 

 _consrvd          *********** *********************** *************



 _aln.pos    690    700    710    720    730    740

3kc6A   EGTAGVESAVLRGFLILGKEDKRYGPALSINELSNLAKGEKANVLIGQGDVVLVMKRKR--------- 

Assign_3 EGTSGVESAVLRGFLILGKEDKRYGPALSINELSNLTKGEKANVLIGQGDVVLVMKRKRDSSILTDSQ 

 _consrvd *** ******************************** **********************



 _aln.p 750

3kc6A   ----------- 

Assign_3 TATKRIRMAIN 

 _consrvd





Step 4 - Building a model and evaluation
From there, using Modeller, we build 5 different PDB files.

>> Summary of successfully produced models:

Filename             molpdf   DOPE score  GA341 score

----------------------------------------------------------------------

Assign_3.B99990001.pdb    7347.70703  -44088.21484    0.99814

Assign_3.B99990002.pdb    12233.39160  -41907.59766    0.88976

Assign_3.B99990003.pdb    9845.06641  -42905.60938    0.99995

Assign_3.B99990004.pdb    8629.17090  -42848.29688    0.94857

Assign_3.B99990005.pdb    11363.01953  -42244.12500    0.99804



looking at the molpdf score, we see that models 1,3, and 4 looks promising, and by looking at the GA341 we end up between model 1 and 3. Now even though the DOPE score is different, it's not that big, so we go with Model 1 because molpdf is much lower.



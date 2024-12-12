# Assignment IV: Comparative Protein Structure Modeling Using VMD

## Objective and Challenge

This assignment aims to enhance your skills in protein modeling and refinement by:

1. Refining the 3D model of the Pb2 protein created in Assignment III.
2. Using three templates (PDB IDs: 8H69_C, 7QTL_C, 8Y7M_C) to optimize your model with VMD and NAMD.
3. Comparing improvements based on each template.
4. Selecting the best-refined model using inference and validation metrics.


## Tasks Breakdown

### Task 1: Review and Optimization of Assignment III

1. Analyze Previous Model:
    - [x] Review your model from Assignment III for potential weaknesses in alignment, quality, or stability.
    - [x] Address missing "log" files or incomplete workflows in your submission.

2. Improve Model:
    - [ ] Include more alignment hits for structural comparison, as more hits might lead to better results (refer to Amber’s logs for guidance).
    - [x] Assess the impact of molpdf scores on model selection ([helpful link](https://salilab.org/modeller/tutorial/cryoem/assess.html)).

3. Redo Assignment III (if necessary):
    - [x] If your model can be improved, redo the assignment and submit both the new workflow and results. Highlight improvements made in the report.

### Task 2: Template Selection and Preparation

1. Download Templates:
    - [x] Retrieve PDB structures **8H69_C, 7QTL_C, and 8Y7M_C** from the Protein Data Bank.

2. Inspect Templates in VMD:
    - [X] Load and analyze their compatibility with the **Pb2 protein sequence** (e.g., length, domain similarities).
    - [x] Perform structural alignment of your model with each template to identify deviations.

3. Quantify Deviations:
    - [x] Use tools like **RMSD** calculations and visual inspections in VMD to assess alignment accuracy.

### Task 3: Comparative Modeling with VMD/NAMD

1. Energy Minimization:

    - [ ] Use VMD to load the Pb2 protein model.
    - [ ] Run NAMD simulations for energy minimization to reduce steric clashes and optimize geometry.

2. Simulations:

    - [ ] Refine the model further through molecular dynamics simulations.

3. Model Evaluation:

    - [ ] Assess the quality of refined models using:
    - [ ] RMSD and Ramachandran plots.
    - [ ] Stability from simulation results.
    - [ ] Structural quality scores.
    - [ ] Compatibility with experimental data, if available.

### Task 4: Reporting

1. Document All Steps:
    - [ ] Detail the methods for energy minimization, simulation parameters, and evaluation metrics.
    - [ ] Describe challenges and how they were resolved.

2. Comparison Table:
    - [ ] Include a table comparing models based on structural quality and stability metrics.
    - [ ] Highlight differences and deviations for specific residues across templates.

3. What are the residues in deviated portions?

4. Final Report:
Format the report like a scientific paper, including:
- [ ] Abstract
- [ ] Introduction
- [ ] Materials and Methods
- [ ] Results
- [ ] Discussion
Use your skills from Assignments I and II to create a well-structured draft.



## Supports and References
https://www.ebi.ac.uk/about/news/updates-from-data-resources/compare-experimental-and-predicted-structures-with-pdbe-kb/
https://www.bakerlab.org/wp-content/uploads/2020/01/Yang2020_ImprovedStructurePredictionInterresidueOrientations.pdf
https://pmc.ncbi.nlm.nih.gov/articles/PMC4321859/
https://www.mdpi.com/2218-273X/13/2/328
https://pmc.ncbi.nlm.nih.gov/articles/PMC2808711/


>Target|Final_Assignment
MERIKELRDLMSQPRTREILTKTTVDHMAIIKKYTSGRQEKNPALRMKWMMAMKYPITADKRIMEMIPERNEQGQTLWSKTNDAGSDRVMVSPLAVTWWNRNGPTTSTVHYPKVYKTYFEKVERLKHGTFGPVHFRNQVKIRRRVDINPGHADLSAKEAQDVIMEVVFPNEVGARILTSESQLTITREKKEELHDCKIAPLMVAYMLERELVRKTRFLPVAGGTSSVYIEVLHLTQGTCWEQMYTPGGEVRNDDVDQSLIIAARNIVRRATVSADPLASLLEMCHSTQIGGVRMVDILRQNPTEEQAVDICKAALGLRISSSFSFGGFTFKRTSGSSVKKEEEVLTGNLQTLKIRIHEGYEEFTMVGRRATAILRKATRRLIQLIVSGRDEQSIAEAVIVAMVFSQEDCMIKAVRGDLNFVNRANQRLNPMHQLLRHFQKDAKVLFQNWGIEPIDNVMGMIGILPDMTPSTEVSLRGVRVSKMGVDEYSSTERVVVSIDRFLRVRDQRGNVLLSPEEVSETQGTEKLTITYSSSMMWEINGPESVLVNTYQWIIRNWETVKIQWSQDPTMLYNKMEFEPFQSLVPKAARGQYSGFVRTLFQQMRDVLGTFDTVQIIKLLPFAAAPPEQSKMQFSSLTVNVRGSGMRILVRGNSPVFNYNKATKRLTILGKDAGALTEDPDEGTSGVESAVLRGFLILGKEDKRYGPALSINELSNLTKGEKANVLIGQGDVVLVMKRKRDSSILTDSQTATKRIRMAIN
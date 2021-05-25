EJP-RD and Helis Academy Pathway Analysis Practical
==============================================================================
## Date: 25 May, 2021
## Instructors: Dr. Friederike Ehrhart and Dr. Lauren J. Dupuis
-----------------------
Pathway analysis helps you to interpret the data in a biologically meaningful context. We will use the data from the paper “Transcriptome 
analysis of human brain tissue identifies reduced expression of complement complex C1Q Genes in Rett syndrome“ by Lin et al. published in Cancer Epidemiology, 
BMC Genomics in 2016 (see [paper](https://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-016-2746-7)). You will need the WikiPathways human pathways collection that you can download [here](http://www.wikipathways.org/wpi/batchDownload.php?species=Homo%20sapiens&fileType=gpml&tag=Curation:AnalysisCollection) as a 
zip file. You will need to unzip it before use. You will also need to download the identifier mapping database for homo sapiens from BridgeDb which can be found [here](https://zenodo.org/record/3667670/files/Hs_Derby_Ensembl_91.bridge?download=1).

The pre-processed dataset we will use for analysis can be downloaded [here](RETT_vs_control_FC_filtered.txt).

## Part 1: Open a Pathway in PathVisio
---------------------------------------------

Begin by starting PathVisio. Open the "Hs_Microglia_Pathogen_Phagocytosis_Pathway_WP3937_94208" pathway from the WikiPathways collection you downloaded.

Small numbers above data nodes, interactions or the info box in the top left of the pathway indicate publication references. 
Double click the *info box in the top left (Title, Availability, Last modified, Organism) and go to the “Literature” tab. There you can see if there are any literature references for the pathway. 


Click on any of the genes in the pathway. Here you can see which identifier and database the gene is annotated with by checking the “Backpage” 
tab on the right side.  

**Load the identifier mapping database:** 
1.	Go to Menu Data → Select Gene Database → Browse to Hs_Derby_Ensembl_91.bridge in the Data folder
2.	Check the status bar at the bottom to see if the gene database has been loaded correctly. 

Now if you click on any of the genes and go to the “Backpage” tab, you will also find other identifier(s) for this gene.  


## Part 2: Data Import in PathVisio
-------------------------------------------
> **Find the correct database.** Open the statistical analysed data in Excel (RETT_vs_control_FC_filtered.txt in Pathway_Analysis_Data folder). The first column 
> contains the identifier of the genes (ENSG_ID). From which of the three databases below are the identifiers in the dataset? 
> *(Required for following steps!)*
>
> - [ ]    Ensembl
> - [ ]    Entrez Gene
> - [ ]    OMIM

Import the data as described below. Go through the different dialogs. 

Steps data import:
1.	Menu “Data” → Import expression Data
2.	Select the RETT syndrome dataset (RETT_vs_control_FC_filtered.txt that you have downloaded) as the input file. Everything else 
should be filled in automatically (see Figure 2a).
3.	In the next dialog, make sure the correct separators are used. You should see the different columns in the preview (see Figure 2b).

![Figure 2A and 2B](https://github.com/LaurenDupuis/Helis-Academy-Omics-June-2019/blob/master/images/Figure_2A_2B_PA.png?raw=true)


4.	Important: in the next step you need to select the column that contains the gene identifier and the database (system code) for 
the identifier. Select the database you chose in question 2A (Note: if the database is wrong your identifiers will not be recognized 
correctly), see Figure 2c. 
5.	Now the data is imported (see Figure 2d). 

![Figure 2C and 2D](https://github.com/LaurenDupuis/Helis-Academy-Omics-June-2019/blob/master/images/Figure%202C_2D_PA_.png?raw=true)

> **Important:** if the number of rows is the same as the number of identifiers not recognized the data import was not done correctly - 
> you probably didn’t select the correct database (step 4 data import)! Redo the import or ask one of the instructors for help. 
> **(Required for following steps!)**

### **Check before you continue!**

If you clicked finish, you should see a default visualization on the pathway (if all genes are gray, the data import was not 
successful → please redo the import, make sure you select the correct database in step 4, otherwise ask one of the instructors). 
Click on the C1QA gene and check the “Data” tab on the right side → do you see the expression data?

-----------------------------------------------------------------------------------------------------------------------------------

## Part 3: Creating a Basic Visualization
Follow the instruction to create a basic visualization. We will visualize the logFC as a contionuous gradient so we can see the 
differences in expression 
1.	Go to Data → Visualization Options
2.	Create a new visualization named “basic visualization”

![Figure 3A](https://github.com/LaurenDupuis/Helis-Academy-Omics-June-2019/blob/master/images/Data_Vis_1_PA_.png?raw=true)


3.	Select “Expression as color” and “Text label”. 
4.	In “Expression as color” select “Basic”.
5.	Check the checkbox before “logFC” and define a new color set.

![Figure 3B](https://github.com/LaurenDupuis/Helis-Academy-Omics-June-2019/blob/master/images/Data_Vis_2_PA_.png?raw=true)

6.	Select “Gradient” and define a gradient from -1 over 0 to 1 (blue - white - red) → Click OK.

![Figure 3C](https://github.com/LaurenDupuis/Helis-Academy-Omics-June-2019/blob/master/images/Data_Vis_3_PA_.png?raw=true)


*What do the colors in the pathway mean biologically?* (Hint: Check the “Legend” tab) 
 

You can check the logFC on a specific gene by clicking it and going to the “Data” tab. 

## Part 4: Create an Advanced Visualization
PathVisio also allows users to visualize multiple data columns together. For that we need to create a new advanced visualization. In 
this case we will visualize the logFC as a gradient. We will apply a set cutoff to show whether the p value is significant and show this 
in green.

1.	Go to Data → Visualization Options
2.	Create a new visualization named “advanced visualization”
3.	Select “Expression as color” and “Text label”. 
4.	In “Expression as color” select “Advanced”.
5.	Check the checkbox before “LogFC” and define a new color set, see Figure 3a.
6.	Select “Gradient” and define a gradient from -1 to 0 to 1 (blue - white - red) → Click OK (same as in simple visualization).
7.	Check the checkbox before “P.Value” and define a new color set, see Figure 3b.
8.	At the bottom, click on “Add Rule”. Go to the text field next to “Rule Logic” and specify the following criteria: [P.Value] < 0.05. Then click on color and select a light green. Click OK and OK, see Figure 3c. 

![Figure 4](https://github.com/LaurenDupuis/Helis-Academy-Omics-June-2019/blob/master/images/Fig4.png?raw=true)

What do the colors in the different columns on the data nodes in the pathway mean biologically? (Hint: Check the “Legend” tab on the right side). 


-------------------------------------------------------------------------------------------------------

## Part 5: Perform Pathway Statistics

To identify pathways that might be affected by RETT syndrome, you can perform pathway statistics to calculate Z-Scores for each pathway. 
PathVisio automatically ranks the pathways based on the Z-Score. 

1.	Go to Menu Data → Statistics
2.	First we need to define a criteria for differentially expressed genes. We are going to select those genes based on significant p-value but we are also going to make sure the change is high enough by specifying a logFC threshold:
    a.	([logFC] < -0.58 OR [logFC] > 0.58) AND [P.Value] < 0.05

3.	Now we need to specify the pathway directory. In the Pathway_Analysis_Data folder you can find the directory: 
Wikipathways-Human-Pathways
4.	Browse to this directory and select it. 
5.	Then click on Calculate and wait for the result table.

What are the top 5 altered pathways and what are their Z-Scores? Do you see highly ranked pathways in the result 
table that you expect to be affected by RETT syndrome?






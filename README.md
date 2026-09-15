## From Differential Expression to Mechanism: Protein–Protein Interaction Network Analysis with STRING Workshop 2026
Differential expression analysis (e.g., DESeq2, limma) is powerful for identifying molecules whose expression changes across conditions. However, it often yields long gene lists that can be difficult to interpret biologically. Pathway analysis methods such as over-representation analysis (ORA) and Gene Set Enrichment Analysis (GSEA) summarize results by testing overlap between differentially expressed genes and predefined signatures, but typically do not explicitly incorporate known molecular interactions among the genes. Protein–protein interaction (PPI) network analysis helps translate a list into biology by placing differentially expressed genes into the context of known and predicted molecular interactions. This context can reveal coordinated pathways and protein complexes, highlight modules of functionally related genes, and help prioritize candidate “key” (hub) proteins that connect multiple altered processes—supporting hypothesis generation and targeted follow-up.
In this hands-on workshop, participants will use Cytoscape and the STRING database (via stringApp) to build and analyze a PPI network from a DESeq2-derived list of differentially expressed genes from Alzheimer’s disease fusiform gyrus data.

### Requirements:
Download and install Cytoscape https://cytoscape.org/download.html

#### Download and install the following apps:

stringApp https://apps.cytoscape.org/apps/stringapp

Enrichment Map https://apps.cytoscape.org/apps/enrichmentmap

Autoannotate https://apps.cytoscape.org/apps/autoannotate

cytoHubba https://apps.cytoscape.org/apps/cytohubba

#### In this session, attendees will learn:

#### Loading the differential expression results to Cytoscape with the stringApp
- Filter the DESeq2 differential analysis results for Log2FC absolute value >= 0.5 and adjusted p-value <0.05
- Load the list of differentially expressed genes to Cytoscape
- Generate the protein-protein interaction (PPI) network
- Turn off (deselect) the STRING annotation columns: tissue, compartment

#### Protein interaction network enrichment analysis with stringApp
- Run the enrichment analysis on the network from stringApp panel
- Filter enrichment results to remove redundant terms
- Cluster the enrichment results with Enrichment map app 0.3 Jaccard coefficient cutoff
- Use Autoannotate app layout, labels, shapes, etc. to modify the network view
- From Autoannotate app panel, select top relevant clusters
- Create a new network with those clusters
- Add new cluster labels with Autoannotate app
- Export as image

#### Protein-protein interaction network clustering with stringApp
- From protein interaction network, cluster the network using the STRING panel MCL clustering tool. Select inflation parameter 3
- From App menu, select STRING Enrichment, retrieve group-wise functional enrichment, maximum number of clusters 20, group size 8
- Look at the enrichment results for the individual clusters and remove redundancy, set filter cutoff to 0.2 for mclCluster 1
- From App menu, select STRING Enrichment, retrieve group-wise annotations, maximum number of clusters 20, group size 8

#### Finding top hubs of the PPI network
- Open cytoHubba app
- Go to the main protein-protein interaction network. From the cytoHubba app, calculate all the node’s scores.
- Select the Hubba nodes Top 10 and rank by Betweenness, submit
- Go to Cytoscape Style tab and change the node label to display name to see the gene symbols

### Additional exercises

#### Importing differential analysis expression values and overlaying on the network
- From main menu, select File, import table from file and select the table with differential analysis results
- Go to the Cytoscpe Style column and change the Fill Color column to Log2 fold change and Mapping Type to continuous, a color scale will appear. Click on it and adjust maximum and minimum of scale as needed
- From the Cytoscape Filter tab, add a column filter for Log2fold change and set the filter between 0 and maximum value (upregulated genes)
- With those selected create a new network
- Repeat the same for down regulated genes
- Analyze those subnetworks

#### Visualizing proteins that are part of a pathway or function
- Go back to the original PPI network and from the STRING Enrichment results tab, select Synapse. All proteins from the network that overlap with this term with highlight
- From Apps, Circular layout, Selected nodes only. Move the resulting circle of protein out of network. Notice that those are mostly down regulated (blue proteins)
- Do the same for Inflammatory Response. Notice that most of these proteins are up-regulated

#### Data

The data used in this workshop comes from an **Alzheimer's Disease (AD) vs control**
gene expression study [GSE125583](https://pmc.ncbi.nlm.nih.gov/articles/PMC10225579/).

| File / Folder | Description |
|---|---|
| `ppi_network.pdf` | Workshop slide deck |
| `AD_vs_ctrol_male.csv` | DESeq2 differential analysis
| `DEGs_AD_vs_ctrol_malelogfc05padj005.csv` | DEGs filtered by Logfoldchange and padj for network analysis
| `male_AD_vs_ctrol_ppi_network.cys` | Cytoscape session file with protein-protein interaction network analysis

#### License

This repository is licensed under the [MIT License](LICENSE).

---

#### Contact

**Workshop Instructor**

For questions, issues, or feedback, please
**[open a GitHub Issue](../../issues/new)** in this repository.

We welcome contributions, corrections, and suggestions from all participants!
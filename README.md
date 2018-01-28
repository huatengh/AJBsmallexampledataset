# AJBsmallexampledataset
a small example package for CLASSIPHY:

simphy_controlfile: Simphy control file used to simulate the dataset in this manuscript, can be used in the CLASSIPHY's wrapper function--simphy.simu

simphy_simulatedrep.zip: example of gene trees in training data. A zip file of three rep folders from simphy simulation(each has three files：species, locus and gene tree file), these folders can be used as input in the training.data function, which calculates summary statistics on simulated data

estimatedgenetreerep.zip: A zipped folder contains example of gene trees in testing data. For running with empirical data, only two files are needed: an estimated gene tree, and an estimated species tree file. Because in this study, our estimated gene trees were from simulated sequences, the folder contains:
	deep(shallow).G: simulated genealogies from simphy, and modified by customer R script modifygenealogy.R (extending terminal branches and adding outgroup)
	deep(shallow).Seq:simulated sequences from seq-gen based on deep(shallow).G using customer perl script seq-gen.pl
	deep(shallow).bestMLTrees: estimated gene trees from .Seq files using RAxML and raxml_seqgenfile.pl script
The .bestMLTrees files can be used as input (gfile) for the sumstat function. we used s_tree.trees as the input for sfile for this study.

DAPC_testingdata.txt: an example of test dataset-- sumstats calculated from the shallow.bestMLTrees file using the sumstat function. To save computation time, the tscore option was turned off and max.freq was set to 0.0025 so that only two subtree frequencies were computed.

DAPC_trainingdata.txt: an example of training dataset-- sumstats calculated from the three rep folders in simphy_simulatedrep.zip using the training.data function, same setting as above. Note: for running on real data, more rep would be needed here.

the above two files can be used to run dapc analysis using  the classifyData function

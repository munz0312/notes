This one did use GDSC1/2 data for training.
Proposed the DrugS (Drug Response prediction Utilising Genomic features Screening)

Input layer 2078 neurons - 30 gene expression features + 2048 compound features
Hidden layer 1, using 1024 neurons with ReLU activation and a 0.1 dropout rate
Hidden layer 2, using 16 neurons with the same things as HL 1.
Output layer, single neuron which predicted LN IC50 (natural log of IC50)

On the test set (GDSC 1), it got a Pearson Correlation Coefficient of 0.67. When compared to other models, CaDRReS_SC was similar and Precily was slightly lower in correlation.

As for MSE, no significant differences.

When tested by cancer type, DrugS did get highest median PCC=0.7

What's good about the model is that it incorporates compound-specific features from the SMILES strings of the drugs - Morgan fingerprint. CaDRReS_SC can't do this.
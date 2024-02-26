# ATP-Deep
Prediction of Protein-ATP Binding Residues Using Multi-view Feature Learning via Contextual-based Co-attention Network

Accurately predicting protein-ATP binding residues is critical for protein function annotation and drug discovery. Computational methods dedicated to the prediction of binding residues based on protein sequence information have exhibited notable advancements in predictive accuracy. Nevertheless, these methods continue to grapple with several formidable challenges, including limited means of extracting more discriminative features and inadequate algorithms for integrating protein and residue information. To address the problems, we propose ATP-Deep, a novel protein-ATP binding residues predictor. ATP-Deep harnesses the capabilities of unsupervised pre-trained language models and incorporates domain-specific evolutionary context information from homologous sequences. It further refines the embedding at the residue level through integration with corresponding protein-level information and employs a contextual-based co-attention mechanism to adeptly fuse multiple sources of features. The performance evaluation results on the benchmark datasets reveal that ATP-Deep achieves an AUC of 0.954 and 0.951, respectively, surpassing the performance of the state-of-the-art model. These findings underscore the effectiveness of assimilating protein-level information and deploying a contextual-based co-attention mechanism grounded in context to bolster the prediction performance of protein-ATP binding residues.

# 1. Requirements

Python >= 3.10.6

torch = 2.0.0

pandas = 2.0.0

scikit-learn = 1.2.2

HHblits = 3.3.0

ProtTrans (ProtT5-XL-UniRef50 model)


# 2. Description
The proposed ATP-Deep method is implemented using python on torch for 
Protein-ATP binding residue prediction. 
The ATP-Deep model utilizes a multi-view features learning strategy to fuse 
the protein language models and domain-specific evolutionary context embedding via 
a contextual-based co-attention network and augmented residue 
feature with its corresponding protein-level information.

# 3 Datasets

atp-388.txt: this file contains 388 ATP binding proteins used for model training

atp-41-for-388.txt: this file contains 41 ATP binding proteins used for model test

atp-227.txt:this file contains 227 ATP binding proteins used for model training

atp-17-for-227.txt: this file contains 17 ATP binding proteins used for model test

atp-549.txt: this file contains 549 ATP binding proteins used for model training

atp-202.txt: this file contains 202 ATP binding proteins used for model test

# 4. How to Use

## 4.1 Set up environment for HMM and ProtTrans
1. Download hh-suite v3.3.0 from https://github.com/soedinglab/hh-suite and compile the source.
2. Download UniRef30_2023_02 dataset from https://gwdu111.gwdg.de/~compbiol/uniclust/2023_02/ .
3. Set ProtTrans follow procedure from https://github.com/agemagician/ProtTrans/tree/master.

## 4.2 Extract features

1. Extract HMM feature: cd to the ATP-Deep/feature_extract dictionary, 
and run "python3 extract_hhm.py and python3 generate-hhm-frequency.py",
the HMM matrixs will be extracted to Dataset/hhdatasethhm fold.

2. Extract pLMs embedding: cd to the ATP-Deep/feature_extract dictionary, 
and run "python3 extract_prot.py", the pLMs embedding matrixs will be extracted to Dataset/prot_embedding fold.

## 4.3 Train and test

1. cd to the ATP-Deep dictionary,and run "python3 ATP-Deep.py" for training and testing the model.


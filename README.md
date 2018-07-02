# MHCSeqNet

MHCSeqNet is a MHC Class I ligand prediction library. This library supports Class I peptide/MHC binding probability prediction.

## Installation (From Source)
This library supports only Python 3.4+.
We'll make this library available via pip install later. For now, installing from source is the only way.
1. Clone this repository 
2. This library is developed using these version of external libraries. We cannot guarantee if this library works on older version of these external libraries.
```
numpy==1.14.3
Keras==2.2.0
tensorflow==1.6.0
scipy==1.1.0
```
3. Install setuptools using pip to setup this python library to be able to import from anywhere in the system. (Also ensure that you install ths latest version)
'''
pip install setuptools
'''
4. Run this command to make this library system-wide
'''
python setup.py install
'''

## How to use this library
### Models
There are two version of the models.
- One-hot based model: This model supports only a limited set of MHC protein. The full list of the supported alleles can be found in 
```
PredictionModel/Pretrained Models/one_hot_model/supported_alleles.txt
```
- Sequence based model: This model is trained on the same set of alleles as one-hot based model but is able to predict any MHC alleles as long as the sequence is known. The full list of known MHC allele sequences can be found in
```
PredictionModel/Pretrained Models/sequence_model/supported_alleles.txt
```

### Input
- Peptide: We supports peptide of length 8 - 15 consisted of these amino acids:
```
'A', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'K', 'L', 'M', 'N', 'P', 'Q', 'R', 'S', 'T', 'V', 'W', and 'Y'.
```
- MHC Protein: As described above, there are two version of the models supporting different set of MHC allele.
### Output
- Binding probability: Instead of predicting binding affinity, these models predict binding probability ranging from 0.0 to 1.0 where 0.0 indicates a non-binder and 1.0 indicates a strong binder.

### Sample
Sample scripts of how to use the library is in sample/
  - For prediction using one-hot based model, follow an example in ```sample/OneHotModelPredictionExample.py```
  - For prediction using sequence based model, follow an example in ```sample/SequenceModelPredictionExample.py```
There're also additional samples for training a model but it's not yet thoroughly tested so please use with caution.

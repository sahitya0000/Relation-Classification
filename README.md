# Relation-Classification

Relation Classification - SEMEVAL 2010 task 8 dataset (Master's Thesis)

* Relation classification is a task of assigning predefined relation labels to the entity pairs that occur in texts. 
  * Example: 
  * Sentence: [People]_e1 have been moving back into [downtown]_e2
  * Relation: Entity-Destination(e1,e2) where e1 = people, e2 = downtown 



## Cite Us As 
```
@MastersThesis{Sahitya:2018,
 author = { {Sahitya Patel} and Harish Karnick}, 
 title = {Multi-Way Classification of Relations Between Pairs of Entities}, 
 school = {Indian Institute of Technology Kanpur (IITK)}, 
 address = {India},
 year = 2018, 
 month = 6
}
```

## Presentation 
[Relation-Classification-github.pdf](https://github.com/sahitya0000/Relation-Classification/blob/master/Presentation/Relation-Classification-github.pdf)

## Dataset 
Paper: [SemEval-2010 Task 8: Multi-Way Classification of Semantic Relations Between Pairs of Nominals](http://www.aclweb.org/anthology/S10-1006)

Zip: [SemEval2010_task8_all_data.zip](https://github.com/sahitya0000/Relation-Classification/blob/master/corpus/SemEval2010_task8_all_data.zip)

## Files 
#### Preprocessing of data
 * 01_create_train_test_attn
 * 02_train_val_split
 * 03_data_preprocess
#### Model training 
 * 04_CBGRU_MEA_Model

## Environment 
 * Python 3.5.4 | Anaconda custom (64-bit)
 * Keras 2.1.5
 * Tensorflow 1.4.0
 * CUDA compilation tools, release 8.0, V8.0.44 (nvcc --version)
 * CuDNN 6.0.21
 * Perl

## Running the model without preprocessing 
 1. Get preprocessed data. Download "data_all.npy" from [this-link](https://drive.google.com/open?id=1hfPcxG8YFVx5uMx8rkbH0fSJVbSn3PpT) (94.6 MB) and put it in the folder "./data/". 
 2. Run "04_CBGRU_MEA_Model"
 
## Running the model with preprocessing 

### 01_create_train_test_attn

**Description:** Pre-processing of dataset files

**Reads:**
 * "./corpus/SemEval2010_task8_training/TRAIN_FILE.TXT"
 * "./corpus/SemEval2010_task8_testing_keys/TEST_FILE_FULL.TXT"

**Creates:**
 * "./files/train_attn.txt"
 * "./files/test_attn.txt"

**To Do:**
1. Set the following path in "01_create_train_test_attn"
```python
os.environ['CLASSPATH'] = "H:/Relation-Classification/stanford/stanford-postagger-2017-06-09"
```
2. Run "01_create_train_test_attn"

### 02_train_val_split

**Description:** Spliting of the training data into training and validation data

**Reads:**
 * "./files/train_attn.txt"
 * "./files/test_attn.txt"

**Creates:**
 * "./files/train_attn_sp.txt"
 * "./files/val_attn_sp.txt"
 * "./files/test_attn_sp.txt"

**To Do:**
1. Run "02_train_val_split"


### 03_data_preprocess

**Description:** Generating a single input file for the model

**Creates:**
 * "./data/data_all.npy"

**Steps:**
1. Place "GoogleNews-vectors-negative300.bin" in "./word_embeddings" folder. ([Download-Link](https://drive.google.com/file/d/0B7XkCwpI5KDYNlNUTTlSS21pQmM/edit), [Website-word2vec](https://code.google.com/archive/p/word2vec/))
2. Run "./word_embeddings/GoogleNews-vectors-negative300_bin_to_txt.py" to create "./word_embeddings/GoogleNews-vectors-negative300.txt"
3. Run "03_data_preprocess"


### 04_CBGRU_MEA_Model

**Description:** Model training. Best model is saved in "./model" folder. 

**Steps:** 
1. Run "04_CBGRU_MEA_Model"

**Creates:**
 * "./model/model.keras" - Model 

## Model CBGRU-MEA

![Model CBGRU-MEA](https://github.com/sahitya0000/Relation-Classification/blob/master/Presentation/ch03-cbgru-mea.jpg)

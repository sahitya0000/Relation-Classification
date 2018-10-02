# Relation-Classification

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

## 01_create_train_test_attn

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

## 02_train_val_split

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


## 03_data_preprocess

**Description:** Generating a single input file for the model

**Creates:**
 * "./data/data_all.npy"

**Steps:**
1. Place "GoogleNews-vectors-negative300.bin" in "./word_embeddings" folder. 
2. Run "./word_embeddings/GoogleNews-vectors-negative300_bin_to_txt.py" to create "./word_embeddings/GoogleNews-vectors-negative300.txt"
3. Run "03_data_preprocess"


## 04_CBGRU_MEA_Model

**Description:** Model training. Best model is saved in ./model folder. 

**Steps:** 
1. Run "04_CBGRU_MEA_Model"

**Creates:**
 * "./model/model.keras" - Model 


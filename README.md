# Relation-Classification
## 01_create_train_test_attn

Description: Pre-processing of dataset files. 

Reads: 
"./corpus/SemEval2010_task8_training/TRAIN_FILE.TXT"
"./corpus/SemEval2010_task8_testing_keys/TEST_FILE_FULL.TXT"

Creates: 
"./files/train_attn.txt"
"./files/test_attn.txt"

To Do: 
1. Set the following path in "01_create_train_test_attn"
os.environ['CLASSPATH'] = "H:/Relation-Classification/stanford/stanford-postagger-2017-06-09"
2. Run "01_create_train_test_attn".  

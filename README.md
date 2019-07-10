# HLMethy
**Relabeling candidate m6As with multiple instance learning.**
The misvm package should be installed at first, which can be downloaded from https://github.com/garydoranjr/misvm.
### m6A_model_training.py
**Usage: python {0} positive_dataset negative_dataset method model_file scale_file score_file reserved_file**
This script is used to train a bag level miSVM/MISVM model.

method : method of selection

        0 -- miSVM
        
        1 -- MISVM
        
A bag index file 'bag_index'will be created in current path.

A feature encoding file 'train_features.txt' will be created in current path.

A model file 'svc.pkl' will be created in current path.

A normalized file 'scale.pkl' will be created in current path.

A prediction score file 'score.txt' will be created in current path.

A reserved samples file 'reserved.txt' will be created in current path.

**Example: python m6A_model_training.py ./traindata/train_pos_example.txt ./traindata/train_neg_example.txt 1 svc.pkl scale.pkl score.txt reserved_samples.txt**
### m6A_model_prediction.py
**Usage: python {0} dataset model_file scale_file predict_res**
This script will generate scores to relabel the candidate m6As.
**Example: python m6A_model_prediction.py ./traindata/test_example.txt ./svc.pkl ./scale.pkl predict_res**

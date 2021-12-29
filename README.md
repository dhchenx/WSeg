#  WSeg

A Python library to perform word segmentation in various fields

## Functions

1. Dictionary-based word segmentation methods (BMM, FMM, and BIMM)
2. Hidden Markov Model (HMM)-based word segmentation method

### Examples
Example 1: Dictionary-based methods
```python
from wseg.dict_based import *

s="谁把电动车扼杀在摇篮？"

path='data/30wChinsesSeqDic_clean.txt'
words_dict=read_dict(path)

# print(bimm(s,words_dict))

print(bimm_from_path(s,path))
```
Example 2: HMM-based methods
```python
from wseg.hmm import hmm_train,hmm_cut
input_data="../data/mallrawtext_jieba.txt"
prob_start_file = "prob_start.py"   
prob_emit_file = "prob_emit.py"     
prob_trans_file = "prob_trans.py"   

# train
hmm_train(input_data,prob_start_file,prob_emit_file,prob_trans_file)

# test based on files
test_str="腔内可见数枚结石伴声影"
result= hmm_cut(prob_start_file,prob_trans_file,prob_emit_file,test_str)
print(result)
```

## License
The `wseg` project is provided by [Donghua Chen](https://github.com/dhchenx/umls-graph). 

# Natural-language-processing
Please refer to notebook on how to perform Named Entity Recognisation and how to tune the hyperparamters.
train, dev/validation, test data used are .conll files in the current folder.

## Experiments
I tried below values for each hyperparameter, and the avg f1 score on the dev dataset will be the criteria to choose the best parameter settings.

`
**Table of hyperparameter tuning validation f1 score**
Training config 
(parameters same as default other than indicated)
Avg f1 score on dev dataset (‘emerging.dev.conll’)
Default
'batch_size': 4, 'half_window': 2, 'embed_dim': 25, 'hidden_dim': 25, 'num_classes': 13, 'freeze_embeddings': False, 'lr': 0.02, 'epochs': 100
‘Num_layers’: 1
0.8824671395802548
Batch_size 2
0.8786100406439366
Batch_size 8
0.8824671395802548
Embed_dim 50
0.8824181390344367
Embed_dim  100 (2nd best)
0.8828044283450783
Embed_dim  200
0.8824118855465907
Embed_dim 300
0.8822393988274964
Half window 3
0.8824036834877962
Half window 4
0.8824963458400458
Half window 5
0.8824354125841017
Hidden dim 50
0.8824671395802548
Hidden dim 100
0.8824631384713871
Number layer 2
0.8823476631930625
Number layer 3(best)
0.8828561475496695
Number layer 4
0.8823008878819346
Freeze_embeddings True
0.8823326493950854
Lr 0.002
0.8821357462243560
Lr 0.1
0.8814530901515277
Epochs 200
0.8829305762387519
Epochs 300(improve with epochs)
0.8831023763895041
Combine two parameters
Embed dim 100, num layer 3
0.8820091892966707
`

## Results
Softmax classifier hyperparameter tuning: test avg f1_score = 0.952

From the above table, the most effective parameter is 3 hidden layers(default 1) plus more epochs. To get better results, I also used a learning rate scheduler to reduce the rate by half per 100 epochs. The model was trained for 1000 epochs(when loss converges) and got avg f1 score of 0.952 on test data.

The learning curve and classification report are included in the report.pdf.





# Natural-language-processing
Please refer to notebook on how to perform Named Entity Recognisation and how to tune the hyperparamters.
train, dev/validation, test data used are .conll files in the current folder.

## Results
Softmax classifier hyperparameter tuning: test avg f1_score = 0.952

From the experiments the most effective parameter is 3 hidden layers(default 1) plus more epochs. To get better results, I also used a learning rate scheduler to reduce the rate by half per 100 epochs. The model was trained for 1000 epochs(when loss converges) and got avg f1 score of 0.952 on test data.

The experimental results, learning curve and classification report are included in the report.pdf.





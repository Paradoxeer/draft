# draft
draft code that does not has clear purposes

<h3>#xgboost.cv can choose the best number of tree using cross validation </h3>
```
xgboost.cv(params, dtrain, num_boost_round=10, nfold=3, stratified=False, folds=None, metrics=(), obj=None,
           feval=None, maximize=False, early_stopping_rounds=None, fpreproc=None, as_pandas=True, verbose_eval=None,
           show_stdv=True, seed=0, callbacks=None, shuffle=True)
```

<h4>##customer metrics </h4>
```
def my_recall(preds,dtrain):#preds传入的为预测概率值<br>
    labels=dtrain.get_label()
    preds_result=[1 if preds[i]>0.5 else 0 for i in range(len(preds))]
    return 'recall_score', metrics.recall_score(labels,preds_result, pos_label=1)#必须返回metric的名字和metric的值
调用的时候为feval=my_recall
```

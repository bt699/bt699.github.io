---
layout: post
title:  "机械学习SVM向量机交叉算法SVC，GridSearchCV"
date:   2019-08-06 13:19:48 +0800
categories: sklearn

---
# from sklearn.svm import SVC'#
机器学习SVM向量机交叉算法SVC。
from sklearn.model_selection import GridSearchCV
通过ztop_ai极宽智能模块库mx_svm_cross函数。
# 原代码 #
{% highlight ruby %}
import pandas as pd

#1
fs0='tmp/iris_'
print('\n1# init,fs0,',fs0)
      
x_train=pd.read_csv(fs0+'xtrain.csv',index_col=False)
y_train=pd.read_csv(fs0+'ytrain.csv',index_col=False)
x_test=pd.read_csv(fs0+'xtest.csv',index_col=False)
y_test=pd.read_csv(fs0+'ytest.csv',index_col=False)
df9=x_test.copy()

#2
print('\n2# 建模')
mx = zai.mx_svm_cross(x_train.values,y_train.values)


def mx_svm_cross(train_x,train_y):    
    mx = SVC(kernel='rbf',probability=True)
    param_grid = {'C':[le-3,le-2,le-1,1,10,100,1000], 'gamma':[0.001,0.0001]}
    grid_search = GridSearchCV(mx,param_grid, n_jobs=1,verbose=1)
    grid_search.fit(train_x,train_y)
    best_parameters = grid_search.best_estimator_.get_params()
    mx = SVC(kernel='rbf', C=best_parameters['C'],gamma=best_parameters['gamma'],probability=True)
    mx.fit(train_x,train_y)
    return mx

#3
print('\n3# 预测')

y_pred =mx.predict(x_test.values)
df9['y_predsr']=y_pred
df9['y_test'],df9['y_pred']=y_test,y_pred
df9['y_pred']=round(df9['y_predsr']).astype(int)

#4
df9.to_csv('tmp\iris_forest9.csv',index=False)

print('\n4# df9')
      
print(df9.tail())

#5
dacc =zai.ai_acc_xed(df9,1,False)

print('\n5# mx:mx_sum,kok:{0:.2f}%'.format(dacc))

{% endhighlight %}

# 修改后代码 #

{% highlight ruby %}
import pandas as pd
import sklearn
from sklearn.svm import SVC
from sklearn.model_selection import GridSearchCV

#1
fs0='tmp/iris_'
print('\n1# init,fs0,',fs0)
      
x_train=pd.read_csv(fs0+'xtrain.csv',index_col=False)
y_train=pd.read_csv(fs0+'ytrain.csv',index_col=False)
x_test=pd.read_csv(fs0+'xtest.csv',index_col=False)
y_test=pd.read_csv(fs0+'ytest.csv',index_col=False)
df9=x_test.copy()

#2
print('\n2# 建模')
      
def mx_svm_cross(train_x,train_y):
    mx = SVC(kernel='rbf',probability=True)
    param_grid = {'C':[1,10], 'gamma':[0.001,0.0001]}
    grid_search = GridSearchCV(mx,param_grid, n_jobs=1,verbose=1)
    grid_search.fit(train_x,train_y)
    best_parameters = grid_search.best_estimator_.get_params()
    mx = SVC(kernel='rbf', C=best_parameters['C'],gamma=best_parameters['gamma'],probability=True)
    mx.fit(train_x,train_y)
    return mx
    
mx = mx_svm_cross(x_train.values,y_train.values)




#3
print('\n3# 预测')

y_pred =mx.predict(x_test.values)
df9['y_predsr']=y_pred
df9['y_test'],df9['y_pred']=y_test,y_pred
df9['y_pred']=round(df9['y_predsr']).astype(int)

#4
df9.to_csv('tmp\iris_forest9.csv',index=False)

print('\n4# df9')
      
print(df9.tail())

#5
def ai_acc_xed(df9,ky0=5,fgDebug=True):
    ny_test = len(df9['y_test'])
    ny_pred = len(df9['y_pred'])
    df9['ysub']=df9['y_test']-df9['y_pred']
    df9['ysub2']=np.abs(df9['ysub'])
    
    df9['y_test_div']=df9['y_test']
    df9.loc[df9['y_test'] == 0, 'y_test_div'] = 0.00001
    df9['ysubk']=(df9['ysub2']/df9['y_test_div'])*100
    dfk = df9[df9['ysubk'] < ky0]
    dsum = len(dfk['y_pred'])                                                                            
    dacc = dsum/ny_test*100
    return dacc
dacc =ai_acc_xed(df9,1,False)

print('\n5# mx:mx_sum,kok:{0:.2f}%'.format(dacc))
{% endhighlight %}
# 运行结果 #

{% highlight ruby %}
1# init,fs0, tmp/iris_

2# 建模

3# 预测

4# df9
    SepalLength  SepalWidth  PetalLength  PetalWidth  y_predsr  y_test  y_pred
33          6.4         2.8          5.6         2.1         3       3       3
34          5.8         2.8          5.1         2.4         3       3       3
35          5.3         3.7          1.5         0.2         2       2       2
36          5.5         2.3          4.0         1.3         1       1       1
37          5.2         3.4          1.4         0.2         2       2       2

5# mx:mx_sum,kok:94.74%


{% endhighlight %}

当'C':[1,10]结果为94.74%,当'C':[1,10,100]结果为97.37%


---
layout: post
title:  "name 'ai_acc_xed' is not defined"
date:   2019-08-02 13:19:48 +0800
categories: sklearn

---
# name 'ai_acc_xed' is not defined'#
机器学习线性回归算法 缺少ai_acc_xed函数造成报错。
ModuleNotFoundError: No module named 'ztop_ai'
没有找到ztop_ai模块库，就自定义的一个ai_acc_xed函数。
# 核心代码 #
{% highlight ruby %}
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


{% endhighlight %}

# 原实例 #

{% highlight ruby %}
import pandas as pd
import ztop_ai as zai
#import zwSys
import sklearn
import numpy as np
from sklearn.linear_model import LinearRegression

fs0 ='tmp/iris_'
print('\n1# fs0,',fs0)
      
x_train=pd.read_csv(fs0+'xtrain.csv',index_col=False);

y_train=pd.read_csv(fs0+'ytrain.csv',index_col=False);

print('\n2# train')
      
print(x_train.tail())

print(y_train.tail())

print('\n3# 建模')
      
def mx_line(train_x,train_y):
    mx = LinearRegression()
    mx.fit(train_x,train_y)
    return mx
      
mx = mx_line(x_train.values,y_train.values)



x_test = pd.read_csv(fs0+'xtest.csv',index_col=False)
df9=x_test.copy()
print('\n4# x_test')
      
print(x_test.tail())

#5

print('\n5# 预测')
      
y_pred = mx.predict(x_test.values)

df9['y_predsr']= y_pred

#6
y_test = pd.read_csv(fs0+'ytest.csv',index_col=False)
print('\n6# y_test')
      
print(y_test.tail())

#7

df9['y_test'],df9['y_pred']=y_test,y_pred

df9['y_pred']=round(df9['y_predsr']).astype(int)

df9.to_csv('tmp/iris_9.csv',index=False)

print('\n7# df9')
     
print(df9.tail())

#8
dacc = zai.ai_acc_xed(df9,1,False)

print(dacc)

print('\n8# mx:mx_sum,kok:{0:.2f}%'.format(dacc))
{% endhighlight %}
# 修改实例 #

{% highlight ruby %}
import pandas as pd
#import ztop_ai as zai
#import zwSys
import sklearn
import numpy as np
from sklearn.linear_model import LinearRegression

fs0 ='tmp/iris_'
print('\n1# fs0,',fs0)
      
x_train=pd.read_csv(fs0+'xtrain.csv',index_col=False);

y_train=pd.read_csv(fs0+'ytrain.csv',index_col=False);

print('\n2# train')
      
print(x_train.tail())

print(y_train.tail())

print('\n3# 建模')
      
def mx_line(train_x,train_y):
    mx = LinearRegression()
    mx.fit(train_x,train_y)
    return mx
      
mx = mx_line(x_train.values,y_train.values)



x_test = pd.read_csv(fs0+'xtest.csv',index_col=False)
df9=x_test.copy()
print('\n4# x_test')
      
print(x_test.tail())

#5

print('\n5# 预测')
      
y_pred = mx.predict(x_test.values)

df9['y_predsr']= y_pred

#6
y_test = pd.read_csv(fs0+'ytest.csv',index_col=False)
print('\n6# y_test')
      
print(y_test.tail())

#7

df9['y_test'],df9['y_pred']=y_test,y_pred

df9['y_pred']=round(df9['y_predsr']).astype(int)

df9.to_csv('tmp/iris_9.csv',index=False)

print('\n7# df9')
     
print(df9.tail())

#8
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

dacc = ai_acc_xed(df9,1,False)

print(dacc)

dac = 5

print('\n8# mx:mx_sum,kok:{0:.2f}%'.format(dacc))


{% endhighlight %}

{% highlight ruby %}
1# fs0, tmp/iris_

2# train
     SepalLength  SepalWidth  PetalLength  PetalWidth
107          6.3         2.8          5.1         1.5
108          6.4         3.1          5.5         1.8
109          6.3         2.5          4.9         1.5
110          6.7         3.1          5.6         2.4
111          4.9         3.1          1.5         0.1
     xid
107    3
108    3
109    1
110    3
111    2

3# 建模

4# x_test
    SepalLength  SepalWidth  PetalLength  PetalWidth
33          6.4         2.8          5.6         2.1
34          5.8         2.8          5.1         2.4
35          5.3         3.7          1.5         0.2
36          5.5         2.3          4.0         1.3
37          5.2         3.4          1.4         0.2

5# 预测

6# y_test
    xid
33    3
34    3
35    2
36    1
37    2

7# df9
    SepalLength  SepalWidth  PetalLength  PetalWidth  y_predsr  y_test  y_pred
33          6.4         2.8          5.6         2.1  2.448323       3       2
34          5.8         2.8          5.1         2.4  2.790113       3       3
35          5.3         3.7          1.5         0.2  1.906942       2       2
36          5.5         2.3          4.0         1.3  1.682549       1       2
37          5.2         3.4          1.4         0.2  1.699024       2       2
44.73684210526316

8# mx:mx_sum,kok:44.74%
{% endhighlight %}

ModuleNotFoundError: No module named 'ztop_ai'
没有找到ztop_ai模块库，就自定义的一个ai_acc_xed函数。
删除zai.部分，在p198页发现效果评估函数，打印dacc显示为None，后发现函数未设置返回，ai_acc_xed函数添加return dacc后程序成功运行。


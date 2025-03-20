# MobilePricePrediction
EDA


[ ]
import numpy as np
import pandas as pd
import seaborn as sns
READ THE DATA


[ ]
dt = pd.read_csv('/content/train.csv')
DATA INFORMATION


[ ]
dt.info()
DATA DESCRIPTION


[ ]
dt.describe()
DATA VISUALIZATION


[ ]
sns.boxplot(dt)


[ ]
sns.boxplot(dt['fc'])


[ ]
dt['fc'].shape
(2000,)

[ ]
q1 = dt['fc'].quantile(0.25)
q3 = dt['fc'].quantile(0.75)
iqr = q3 -q1
lb = q1 - 1.5*iqr
ub = q3 + 1.5*iqr
l = np.where(dt['fc'] <= lb)[0]
u = np.where(dt['fc'] >= ub)[0]
dt.drop(index = l,axis=0,inplace = True)
dt.drop(index = u,axis=0,inplace = True)

[ ]
dt['fc'].shape
(1958,)

[ ]

Start coding or generate with AI.

[ ]
sns.boxplot(dt['fc'])


[ ]
sns.boxplot(dt['px_height'])


[ ]
dt['px_height'].shape
(1958,)

[ ]
q1 = dt['px_height'].quantile(0.35)
q3 = dt['px_height'].quantile(0.95)
iqr = q3 -q1
lb = q1 - 1.5*iqr
ub = q3 + 1.5*iqr
l = np.where(dt['px_height'] <= lb)[0]
u = np.where(dt['px_height'] >= ub)[0]
dt.drop(index = l,axis=0,inplace = True)
dt.drop(index = u,axis=0,inplace = True)

[ ]
dt['px_height'].shape
(1956,)

[ ]
sns.boxplot(dt['px_height'])


[ ]
sns.boxplot(dt['three_g'])


[ ]
dt['three_g'].shape
(1956,)

[ ]
from sklearn.preprocessing import StandardScaler
sc=StandardScaler()
dt=sc.fit_transform(dt)

[ ]
sns.boxplot(dt)

## its saample of project

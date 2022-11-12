<center> Readme Stage 3 </center>
Kami mengimport banyak libraries, antara lain :
- import numpy as np
- import pandas as pd
- import matplotlib.pyplot as plt
- import seaborn as sns
- from matplotlib import rcParams
- from scipy import stats
- from sklearn.preprocessing import StandardScaler
- from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score, roc_auc_score
- from sklearn.model_selection import cross_validate
- import warnings
- from sklearn.tree import DecisionTreeClassifier
- from sklearn.model_selection import RandomizedSearchCV, GridSearchCV
- from scipy.stats import uniform
- from sklearn.ensemble import RandomForestClassifier
- from sklearn.linear_model import LogisticRegression
- from xgboost import XGBClassifier
<br>
Setelah itu kami menyiapkan dataset kami, beberapa hal yang kami lakukan :
- Mengisi missing value
- Mengecek adanya duplikat data atau tidak (apabila ada hapus)
- Mengecek outlier (dalam modeling ini kamu tidak menghapus outlier, karena kami menginginkan model yang robust akan outlier)
- Membuat fitur baru (`country_type`, `total_guest`, `total_stay`, `musim_arrival`, `musim_rsv`)
- Melakukan fitur encoding kepada 12 kolom
- Melakukan drop pada 30 kolom
- Mengecek Class Imbalance
<br>
Terakhir, kami melakukan modelling, ada 4 model yang kita pakai : 
- Decision Tree
- Random Forest
- Linear Regression
- XGBoost
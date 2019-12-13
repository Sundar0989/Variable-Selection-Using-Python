# XVerse

**XVerse** short for **X**-uni**Verse** is a Python module for machine learning in the space of feature engineering, feature transformation and feature selection.  

## Installation

The package requires `numpy, pandas, scikit-learn, scipy` and `statsmodels`. In addition, the package is tested on Python version 3.5 and above.

To install the package, download this folder and execute:
```sh
python setup.py install
```
or
```sh
pip install xverse
```
or 
```sh
conda install -c conda-forge xverse
```

## Usage

XVerse module are fully compatible with sklearn transformers, so they can be used in pipelines or in your existing scripts. Currently, it supports only Pandas dataframes. 

## Example

### Monotonic Binning
```python
from xverse.transformer import MonotonicBinning

clf = MonotonicBinning()
clf.fit(X, y)

print(clf.bins)
```
```
{'age': array([19., 35., 45., 87.]),
 'balance': array([-3313.        ,   174.        ,   979.33333333, 71188.        ]),
 'campaign': array([ 1.,  3., 50.]),
 'day': array([ 1., 12., 20., 31.]),
 'duration': array([   4.        ,  128.        ,  261.33333333, 3025.        ]),
 'pdays': array([-1.00e+00, -5.00e-01,  1.00e+00,  8.71e+02]),
 'previous': array([ 0.,  1., 25.])}
```

### Weight of Evidence (WOE) and Information Value (IV)
```python
from xverse.transformer import WOE

clf = WOE()
clf.fit(X, y)

print(clf.woe_df.head())
```
```
	Variable_Name	Category	Count	Event	Non_Event	Event_Rate	Non_Event_Rate	Event_Distribution	Non_Event_Distribution	WOE	Information_Value
0	age	(18.999, 35.0]	1652	197	1455	0.119249	0.880751	0.378119	0.36375	0.038742	0.024693
1	age	(35.0, 45.0]	1388	129	1259	0.092939	0.907061	0.247601	0.31475	-0.239961	0.024693
2	age	(45.0, 87.0]	1481	195	1286	0.131668	0.868332	0.374280	0.32150	0.152007	0.024693
3	balance	(-3313.001, 174.0]	1512	133	1379	0.087963	0.912037	0.255278	0.34475	-0.300465	0.061574
4	balance	(174.0, 979.333]	1502	163	1339	0.108522	0.891478	0.312860	0.33475	-0.067629	0.061574
```




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

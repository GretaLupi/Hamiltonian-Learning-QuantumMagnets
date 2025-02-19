# Datasets Structure

This document describes the structure of the datasets used in the project.

## Fermionic Chain Dataset

The Fermionic Chain dataset is stored in a CSV file and loaded into pandas using `pd.read_csv()`. The structure of the dataframe is as follows:

- **Target Parameters**: The last three columns represent the target parameters:
  - $\mu$ : *chemical potential*
  - $t_2$ : *second neighbours hopping*
  - $\lambda_R$ : *Rashba coupling*
  
  These columns are extracted and stored in `y_data`.

- **Input Features**: The remaining columns represent the input data for training the model:
  - `X_data`: Contains all features, excluding the target parameters.
  - `X_data_dos`: Contains the first 450 columns, representing the Density of States (DOS).
  - `X_data_dosf`: Contains the next 450 columns (columns 451 to 900), representing the Fourier transform of the DOS.
 
### Key Dataset Parameters:
- Number of samples: 5000
- Number of energy biases: 3
- Number of fermions: 150

---

## Spin Chain Dataset

The Spin Chain datasets are stored in a CSV file and loaded into a pandas dataframe using `pd.read_csv()`. The structure of the dataframe is as follows:

- **Target Parameters**: The last three columns represent the target parameters in the following order:
  - $J_2$ : *second neighbours exchange*
  - $J_z$ : *anysotropic exchange*
  - $J_{DM}$ : *Dzyaloshinskii–Moriya exchange*
  
  These columns are stored in `y_data`.

- **Input Features**: All columns preceding the target parameters represent the input features and are stored in `X_data`.

### Key Dataset Parameters:
- Number of samples: 2000
- Length of the magnetic field vector ($B_z$ or $B_x$): 12
- Number of spins: 21

---

## Usage
After loading, the target parameters are extracted and stored separately in `y_data`, while the input features are stored in `X_data`, `X_data_dos`, and `X_data_dosf` as required by the model.

Make sure to properly handle the extraction of target and feature columns based on the dataset structure outlined above.

For the Fermionic Chain:

```python
import pandas as pd

df = pd.read_csv('./datasets/ferm_chain_data.csv')

y_data = np.zeros((5000,3))
y_data[:,0] = df['mu_values'].values
y_data[:,1] = df['t2_values'].values
y_data[:,2] = df['lam_values'].values

X_data = df[df.columns[:-3]].values # if use both

X_data_dos = df[df.columns[:450]].values # DOS
X_data_dosf = df[df.columns[450:900]].values # Fourier DOS
```

For the Spin Chain:

```python
import pandas as pd
df = pd.read_csv('./datasets/spinchain_data_Bz.csv') # Bz
#df = pd.read_csv('./datasets/spinchain_data_Bz.csv') # Bx

y_data = df[df.columns[-3:]].values
X_data = df[df.columns[:-3]].values

```
PCA was used to reduce data dimensionality before training the spin chain models.
The specific code is not included here, but it can be implemented using `sklearn.decomposition.PCA`. For a detailed explanation of its methodology and impact on model performance, see the accompanying paper.

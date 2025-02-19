# Usage Guide

## 1. Loading Data
The dataset and pre-trained models are provided in the repository. To load them:

```python
import pandas as pd

data = pd.read_csv("data/dataset.csv")
```
For more details, refer to [datasets_structure.md](datasets_structure.md).

## 2. Adding Gaussian Noise
To improve model robustness, Gaussian noise can be added to the training and test data:

```python
import numpy as np

def add_gaussian_noise(data, std_dev_noise=0.1):
    """
    Add Gaussian noise to the data.
    
    Parameters:
    data (np.ndarray): Dataset to which noise will be added.
    std_dev_noise (float): Standard deviation of the Gaussian noise.
    
    Returns:
    np.ndarray: Dataset with added noise.
    """
    noisy_data = np.zeros(data.shape)

    for i in range(data.shape[0]):
        measurement_noise = np.random.normal(loc=0, scale=std_dev_noise, size=data.shape[1])
        noisy_data[i, :] = data[i, :] + measurement_noise
        
    return noisy_data
```

Example usage:
```python
noisy_data = add_gaussian_noise(data)
```

## 3. Fidelity Calculation
This function calculates the fidelity between two distributions:

```python
import numpy as np

def fidelity(true_values, predicted_values):
    """Calculate fidelity between true and predicted values."""
    num = np.mean(predicted_values[:] * true_values[:]) - np.mean(predicted_values[:]) * np.mean(true_values[:])
    den = np.sqrt(np.var(true_values[:])) * np.sqrt(np.var(predicted_values[:]))
    return num / den
```

Example usage:

```python
fid = fidelity(vector1, vector2)
```

## 4. Running the Models

After loading the dataset and applying necessary preprocessing, use the trained models as follows:

```python
from keras.models import load_model

model = load_model("path_to_model.h5")
y_pred = model.predict(X_test)
```

Ensure all dependencies are installed as specified in requirements.txt before running the scripts.


Neural Network Architecture

## Overview

The neural network used for all cases consists of fully connected layers with ReLU activation functions. The architecture remains the same across different datasets, with variations in input features.

## Architecture Details

For the spin chain, the model is structured as follows:

```markdown
| Layer           | Output Shape | Number of Parameters |
|----------------|-------------|----------------------|
| Dense (input)  | (None, 32)  | 672                  |
| Dense          | (None, 32)  | 1056                 |
| Dense          | (None, 16)  | 528                  |
| Dense          | (None, 16)  | 272                  |
| Dense          | (None, 8)   | 136                  |
| Dense          | (None, 8)   | 72                   |
| Dense (output) | (None, 3)   | 27                   |
| __Total__     |             | **986899**           |
```

For the fermionic chain:

```markdown
| Layer           | Output Shape | Number of Parameters |
|----------------|--------------|---------------------|
| Dense (input)  | (None, 512)  | 461312              |
| Dense          | (None, 512)  | 262656              |
| Dense          | (None, 256)  | 131328              |
| Dense          | (None, 256)  | 65792               |
| Dense          | (None, 128)  | 32896               |
| Dense          | (None, 128)  | 16512               |
| Dense          | (None, 64)   | 8256                |
| Dense          | (None, 64)   | 4160                |
| Dense          | (None, 32)   | 2080                |
| Dense          | (None, 32)   | 1056                |
| Dense          | (None, 16)   | 528                 |
| Dense          | (None, 16)   | 272                 |
| Dense (output) | (None, 3)    | 51                  |
| **Total**     |              | **986899**          |
```

## Dataset and Training Details

The datasets are split into training, validation, and test sets:

- Training set: 55%

- Validation set: 25%

- Test set: 20%

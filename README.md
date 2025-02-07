# Hamiltonian Learning Quantum Magnets - Datasets & Models

This repository contains the datasets and models used in the paper:  
**"Hamiltonian Learning of Quantum Magnets with Non-Local Impurity Tomography"**  

## 📂 Contents
- **Datasets:** Numerical simulations for spin and fermionic chains with impurity-based tomography.
- **Machine Learning Models:** Implementations of Hamiltonian learning algorithms.
- **Scripts:** Code for preprocessing, training, and evaluation.

## 📜 Description
Our work explores Hamiltonian learning in quantum magnets using impurity-based tomography. We provide datasets and models to facilitate reproducibility and further research in quantum many-body systems, topology, and machine learning for physics.

## 🔧 Requirements
To use the models, install the required dependencies:
```bash
pip install -r requirements.txt
```

## 📊 Datasets
The repository includes:

- **Spin Chain Datasets** (data/spin_chain/):
  - Contains spin correlation calculations with spin-1 impurity perturbation.
  - Both Bx and Bz case.
- **Fermionic Chain Dataset** (data/fermionic_chain/):
  - Includes impurity responses in fermionic systems
  - Useful for benchmarking Hamiltonian learning methods.

## 🚀 Usage
Running the training script:
To train the Hamiltonian learning model on a specific dataset, use:

```bash
python train_model.py --dataset spin_chain
```
For the fermionic dataset:
```bash
python train_model.py --dataset fermionic_chain
```
Modify config.json to adjust model parameters.

## 📄 Citation
If you use this repository in your research, please cite our paper:

```bibtex
@article{GLupi2024,
  title={Hamiltonian Learning of Quantum Magnets with Non-Local Impurity Tomography},
  author={Greta Lupi and Jose L.Lado},
  journal={Phys. Rev. Applied (under review)},
  year={2024}
}
```

## 🤝 Contributing
If you find this repository useful and wish to contribute, feel free to open an issue or submit a pull request.

## 📬 Contact
For any questions or collaborations, please reach out via email or open an issue in this repository.

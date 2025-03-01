# Hamiltonian Learning Quantum Magnets - Datasets & Models

This repository contains the datasets and models used in the paper:  
[**"Hamiltonian Learning of Quantum Magnets with Non-Local Impurity Tomography"**](https://arxiv.org/abs/2412.07666) arXiv: [2412.07666](https://arxiv.org/abs/2412.07666).

## 📂 Contents
- **Datasets:** Numerical simulations for spin and fermionic chains with impurity-based tomography.
- **Machine Learning Models:** Implementations of Hamiltonian learning algorithms.

## 📜 Description
Our work explores Hamiltonian learning in quantum magnets using impurity-based tomography. We provide datasets and models to facilitate reproducibility and further research in quantum many-body systems, topology, and machine learning for physics.

## 🔧 Requirements
To use the models, install the required dependencies:
```bash
pip install -r requirements.txt
```

## 📊 Datasets
The repository includes:

- **Spin Chain Datasets** (datasets/spinchain_data_Bx.csv & spinchain_data_Bz.csv):
  - Contains spin correlation calculations with spin-1 impurity perturbation.
  - Both $B_x$ and $B_z$ case.
- **Fermionic Chain Dataset** (datasets/ferm_chain_data.csv):
  - Includes impurity responses in fermionic systems
  - Useful for benchmarking Hamiltonian learning methods.

## 📄 Citation
If you use this repository in your research, please cite our paper:

```bibtex
@misc{lupi2024hamiltonianlearningquantummagnets,
      title={Hamiltonian learning quantum magnets with non-local impurity tomography}, 
      author={Greta Lupi and Jose L. Lado},
      year={2024},
      eprint={2412.07666},
      archivePrefix={arXiv},
      primaryClass={cond-mat.mes-hall},
      url={https://arxiv.org/abs/2412.07666}, 
}
```

## 🤝 Contributing
If you find this repository useful and wish to contribute, feel free to open an issue or submit a pull request.

## 📬 Contact
For any questions or collaborations, please reach out via email or open an issue in this repository.

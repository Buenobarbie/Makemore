# Neural Network from Scratch: WaveNet & Name Generator

This repository contains an implementation of a neural network built from scratch using raw Python and PyTorch-like classes. The main goal is to understand the inner workings of neural networks, focusing on key components such as backpropagation, weight initialization, and batch normalization.

The project also includes a **Name Generator**, inspired by Andrej Karpathy's [Neural Networks: Zero to Hero](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ) playlist.

## Key Features
- **Neural Network from Scratch**: Built a neural network without relying on high-level libraries to fully grasp how everything works.
- **Custom PyTorch-like Classes**: Implemented classes like `Linear`, `BatchNorm`, `Embedding`, and `Tanh` to simulate the behavior of PyTorch layers.
- **WaveNet Model**: Created a WaveNet-like architecture to train a name generator model.
- **Animal Name Generator**: Adapted the model to generate names that resemble real animal names, showcasing the versatility of the architecture.

## Setup and Installation

### Prerequisites
- Python 3.x
- PyTorch (preferably a version compatible with your system)
- Matplotlib (for plotting losses during training)

You can install the required dependencies via:

```bash
pip install torch matplotlib
```

### Running the Notebook
The main scripts are `API.ipynb` and `wavenet.ipynb`. The `API.ipynb` file contains the PyTorch-like classes, while `wavenet.ipynb` contains the code to train the name generation model.

Clone the repository:

```bash
git clone https://github.com/yourusername/yourrepository.git
```

Open `wavenet.ipynb` in Jupyter or VS Code and run the code.

To run in Google Colab, simply navigate to the file on GitHub and click the "Open with Colab" button.

### Training the Model
The model is trained on a dataset of names stored in `names.txt`. It uses a vocabulary of characters (`.abcdefghijklmnopqrstuvwxyz`) and builds sequences of characters for training using a sliding window approach.

The model consists of the following key components:

- **Embedding Layer**: Converts input indices into dense vectors.
- **Batch Normalization**: Normalizes activations to improve training.
- **Linear Layers**: Fully connected layers with weight updates.
- **Tanh Activation**: Applied after each layer to introduce non-linearity.

### Model Architecture
The model follows a sequential architecture:

- **Embedding Layer**: Maps each character to a dense embedding.
- **FlattenConsecutive**: Combines consecutive features from previous layers.
- **Linear and BatchNorm Layers**: Apply linear transformations followed by batch normalization and Tanh activation.
- **Output Layer**: Generates the output, predicting the next character in the sequence.

### Training Loop
The training loop runs for a maximum of 200,000 steps. During each step:

- A mini-batch is constructed from the training data.
- The model performs a forward pass to predict the next character in the sequence.
- The loss is calculated using cross-entropy loss.
- Backpropagation is performed to update the model parameters using gradient descent.
- Losses are logged during training and plotted using matplotlib.

### Sample Output
After training, you can sample names generated by the model. For example, the model might generate names like:

```bash
zohie
axan
restez
awalei
kemri
phina
assiza
joce
```

### Model Evaluation
The model is evaluated on training, validation, and test sets. The loss is printed for each split to track the model's performance.

```bash
train 2.116732597351074
val 2.1428780555725098
```

## Key Learnings
- **Neural Network from Scratch**: Built the entire architecture without relying on high-level libraries, gaining a deeper understanding of neural networks.
- **PyTorch-like Class Implementation**: Created custom classes like `Linear`, `BatchNorm`, and `Embedding` to understand the mechanics of popular frameworks.
- **WaveNet Model**: Applied the WaveNet architecture for name generation and extended it to create an animal name generator.


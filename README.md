# Computer Vision Test Task Solution for CHI IT Academy

**Author**
- Oleh Buravenko
- burik15v@gmail.com
- Telegram: @CrunchLover228

## Project Overview
In this project, a solution was developed for the classification of handwritten VIN code characters. Demo notebook, training and evaluating scripts as well as model weights and results curves are provided.

## Used Methods
For such task, a solution was developed for the classification of handwritten VIN code characters. Since our task involves recognizing characters in 28x28 grayscale images, which contain relatively little information for processing, a Convolutional Neural Network (CNN) is both the most efficient and simplest solution in this situation.

Regarding the dataset, the 'balanced' configuration of the Extended MNIST (EMNIST) dataset was chosen, as other options were either imbalanced in terms of class distribution or more specific, such as containing only digits or only letters. Moreover, it was necessary to apply image transformations in the form of a -90-degree rotation and horizontal flipping to achieve the correct image format.

It is also important to consider the case where we need to recognize VIN code characters, which requires filtering the dataset to exclude unnecessary symbols, such as lowercase characters and certain letters like I, Q, and O.

Among the libraries and frameworks utilized in this project, PyTorch stands out as the primary framework for building, training, and inferring the model. Additionally, torchvision was employed for loading and preprocessing the EMNIST dataset.

## Training Results

### Dataset
- EMNIST (Balanced configuration, filtered to exclude lowercase letters and specific symbols like I, O, and Q).
- 82% training, 18% validation split.

### Training Configuration
- Optimizer: Adam
- Loss Function: CrossEntropyLoss
- Learning Rate: 0.001
- Batch Size: 32
- Epochs: 5

### Model:
- Input Shape: 28x28 grayscale images.
- Architecture: CNN with 2 convolutional blocks and 1 fully connected layer.

### Perfomance:

| Epoch | Train Loss | Train Accuracy | Test Loss | Test Accuracy |
|-------|------------|----------------|-----------|---------------|
| 1     | 0.75664    | 79%            | 0.44132   | 85%           |
| 2     | 0.38317    | 87%            | 0.38510   | 86%           |
| 3     | 0.34475    | 88%            | 0.35566   | 88%           |
| 4     | 0.32197    | 89%            | 0.34641   | 88%           |
| 5     | 0.30343    | 89%            | 0.34365   | 88%           |

## Usage Instructions
Run inference file:
```bash
python inference.py <yourpath>\images
```
Run training file:
```bash
python train.py
```
Install depencies and set up the environment
```bash
python3 -m venv myenv
source myenv/bin/activate
pip install -r requirements.txt
```
In any case, you can also see my demo notebook with showing the model's work





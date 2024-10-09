# Instrument Separation in Songs

## Project Overview
The goal of this project is to identify and isolate different instruments within audio files, enabling manipulation of their volumes. For example, decreasing the guitar volume to create a backing track suitable for practice. This involves sound source separation using Python and machine learning techniques.

## PACE Strategy

### Plan
- **Define Features to Extract**
  - Determine whether to use spectrogram, mel-spectrogram, or other audio representations.
  
- **Select Dataset(s)**
  - **MUSDB18**: [Download MUSDB18](https://sigsep.github.io/datasets/musdb.html)
  - **MedleyDB**: [Download MedleyDB](https://medleydb.weebly.com/)
  - **GTZAN Genre Collection**: [Download GTZAN](https://www.robots.ox.ac.uk/~vgg/data/gtzan/)
  
- **Choose Primary Model**
  - **Open-Unmix (UMX)**
    - [GitHub Repository](https://github.com/sigsep/open-unmix-pytorch)
  
- **Outline Architecture**
  - Adapt Open-Unmix for instrument separation tasks specific to the project needs.

### Analyze
- **Data Preprocessing**
  - Apply Short-Time Fourier Transform (STFT) or other necessary preprocessing steps.
  
- **Define Evaluation Metrics**
  - Signal-to-Distortion Ratio (SDR)
  - Source-to-Interference Ratio (SIR)
  
- **Literature Review**
  - Study existing models and techniques to identify best practices and potential improvements.

### Construct
- **Build Pipeline**
  - **Data Loading**: Implement efficient data loaders for the selected datasets.
  - **Model Training**: Set up training routines using PyTorch or TensorFlow.
  - **Evaluation**: Integrate evaluation metrics to monitor model performance.
  
- **Continuous Integration**
  - Utilize GitHub Actions to automate testing, deployment, and model training evaluation.
  
- **API Integration**
  - Explore using Spotify or YouTube APIs to enhance dataset diversity or extend functionality.

### Execute
- **Model Training**
  - Train the selected model on the preprocessed dataset.
  
- **Model Evaluation**
  - Assess model performance using defined metrics and refine as necessary.
  
- **Deployment**
  - Apply the trained model to separate instruments in new songs.
  
- **Insights Generation**
  - Analyze results to derive meaningful insights and document findings.

## Technological Stack
- **Development Environment**
  - GitHub Codespaces for collaborative development and continuous delivery.
  
- **Python Libraries**
  - `librosa`: Audio processing and feature extraction.
  - `PyTorch` or `TensorFlow`: Building and training neural networks.
  - `Open-Unmix (UMX)`: Pre-built models for source separation.
  - `mir_eval`: Evaluation of separation performance.

## Installation
1. **Clone the Repository**
    ```bash
    git clone https://github.com/yourusername/instrument-separation.git
    cd instrument-separation
    ```

2. **Set Up Virtual Environment**
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3. **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

## Usage (Tested in GitHub Actions)

GitHub Actions will run each step automatically during Continuous Integration to validate the pipeline and functionality.

### Step 1: Download Dataset
- **Manual Step**: Follow the links in the [Plan](#plan) section to download and prepare your datasets.
  
### Step 2: Preprocess Data (Tested in GitHub Actions)
```bash
python preprocess.py --dataset musdb18

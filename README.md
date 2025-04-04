# 🎧 Audio Deepfake Detection Using LSTM

This project focuses on detecting audio deepfakes using a deep learning model built with Long Short-Term Memory (LSTM) networks. It leverages MFCC (Mel-Frequency Cepstral Coefficients) features to train a classifier capable of distinguishing between real and fake audio clips.

---

Dataset

The dataset consists of `.wav` audio files organized into two folders:
- `REAL`: Contains authentic audio clips.
- `FAKE`: Contains deepfake/generated audio clips.

 Dataset path used:  
`C:\Users\Naman jain\Downloads\archive\KAGGLE\AUDIO`

---

Model Architecture

The current model is built using a **Stacked LSTM** network with the following layers:
- Input Layer  
- Masking Layer (to ignore padded values)  
- LSTM (64 units) → Dropout  
- LSTM (32 units) → Dropout  
- Dense (16 units, ReLU activation)  
- Output Layer (Softmax for binary classification)

**Optimizer**: Adam  
**Loss Function**: Categorical Crossentropy

---

 Data Preprocessing

1. **MFCC Feature Extraction** from audio signals.  
2. **Data Augmentation**:
   - Time Stretching  
   - Pitch Shifting  
3. **Sequence Padding** to standardize input length.  
4. **One-hot Encoding** for labels.

Model	Description	Pros	Cons
GRU (Gated Recurrent Unit)	A simplified version of LSTM with fewer parameters.	Faster training, good for smaller datasets.	Slightly less expressive than LSTM.
1D CNN	Uses convolution over audio feature sequences.	Efficient and fast. Captures local patterns well.	Limited in modeling long-term dependencies.
Transformer	Attention-based model that learns global dependencies.	Highly accurate for sequence modeling.	Requires large data, expensive to train.
Bi-LSTM	LSTM that learns from both past and future contexts.	Better context understanding.	Slower training, more memory usage.


Why LSTM is best (in many cases):

Learns long-term dependencies

Handles sequence variation

Is relatively lightweight and effective on small to medium datasets

Works well for MFCCs, which are time-based features from audio

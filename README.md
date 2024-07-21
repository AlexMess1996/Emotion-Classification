# EEG Emotion Classification using LSTM and GRU

## Project Overview

This project aims to compare the performance of Long Short-Term Memory (LSTM) and Gated Recurrent Unit (GRU) models in detecting emotions from Electroencephalogram (EEG) signals. The goal is to determine if the computationally cheaper GRU model can achieve accuracy comparable to the LSTM model.

## Motivation

Understanding emotions from EEG signals can unlock significant insights into human brain function, potentially aiding those with mental health issues and enhancing user experiences in various applications. This project explores whether a less computationally intensive model like GRU can be as effective as LSTM in emotion classification.

## Dataset

The dataset "Emotions.csv" contains EEG data from two participants (one male and one female) watching movie clips designed to evoke positive, neutral, and negative emotions. EEG sensors were placed at TP9, AF7, AF7, and TP10 locations according to the international EEG standard.

## Methodology

### Data Preprocessing

- Fast Fourier Transform (FFT) applied to extract frequency domain features.
- Standard Scaler used to normalize the data.
- Data reshaped for LSTM and GRU input requirements.
- Labels one-hot encoded for categorical classification.

### Model Building

- **LSTM Model**: Built using Keras Sequential API with 50 LSTM cells, a dropout layer, and a dense output layer with softmax activation.
- **GRU Model**: Similar architecture to LSTM but with 256 GRU cells and a flatten layer before the dense output layer.

### Model Training

- Compiled with Adam optimizer and categorical crossentropy loss.
- Trained for 20 epochs with a batch size of 32.
- Evaluated using a confusion matrix to assess classification performance.

## Results

| Model | Accuracy | Precision | Recall | F1-score |
|-------|----------|-----------|--------|----------|
| LSTM  | 96.2%    | 96.3%     | 96.2%  | 96.2%    |
| GRU   | 93.2%    | 93.3%     | 93.3%  | 93.3%    |

- **LSTM**: Achieved higher accuracy, making it ideal for applications requiring precise emotion classification.
- **GRU**: Slightly less accurate but computationally cheaper, making it a viable alternative when resources are limited.

## Conclusion

The LSTM model outperforms the GRU model in terms of accuracy. However, the GRU model's reduced computational requirements make it a practical alternative, especially in resource-constrained scenarios. Future work could explore further optimization and testing with different datasets to validate these findings.

## Repository Structure

- `LSTM.ipynb`: Jupyter notebook containing the implementation of the LSTM model.
- `data/`: Directory containing the EEG dataset.
- `results/`: Directory containing the model evaluation results and confusion matrix graphs.

## References

- Bird, J., Ekart, A., & Buckingham, C. (2019). Mental Emotional Sentiment Classification with an EEG-based Brain-machine Interface. [Link](https://doi.org/10.1109/T-AFFC.2011.15)
- Koelstra, S., et al. (2012). DEAP: A database for emotion analysis using physiological signals. [Link](https://doi.org/10.1109/T-AFFC.2011.15)
- Additional references as mentioned in the report.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

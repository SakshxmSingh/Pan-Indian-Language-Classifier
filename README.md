# Language Recognition from Audio for Pan Indian Languages

**CSE343 Machine Learning Project - Monsoon 2024, IIIT-Delhi**

## Abstract

This project addresses the challenge of automatic language identification for Pan Indian languages given India's rich linguistic diversity. We developed a system leveraging classical machine learning techniques on a large audio dataset. By extracting robust acoustic features like MFCCs and Spectral properties, and employing models like SVM and MLP, we demonstrate significant potential for accurately classifying a wide range of Indian languages from audio samples.

## Dataset

*   **Source:** Kaggle dataset by Chaitanya Bharadwaj H B.
*   **Content:** Approximately 257,000 five-second audio samples.
*   **Languages (9):** Bengali, Gujarati, Hindi, Kannada, Malayalam, Marathi, Tamil, Telugu, and Urdu (Punjabi was removed due to data issues).
*   **Origin:** Audio samples sourced from regional YouTube videos.
*   **Preprocessing:** Data cleaning (silence removal, normalization, noise filtering), padding/trimming to 5 seconds.

## Methodology

1.  **Feature Extraction:** Explored various feature sets. The best performing set ("Feature Set 2") included:
    *   25 MFCCs
    *   25 MFCC Deltas
    *   12 Chroma STFT features
    *   5 Spectral Features
2.  **Models Evaluated:**
    *   Random Forest (Baseline)
    *   Support Vector Machine (SVM) (with RBF, Linear, Poly kernels)
    *   Gaussian Mixture Models (GMM)
    *   GMM with Universal Background Model (GMM-UBM)
    *   Hidden Markov Models (HMM)
    *   Multilayer Perceptron (MLP)

## Key Results

*   **Multilayer Perceptron (MLP):** Achieved the highest accuracy of **99.12%** (using 3 hidden layers: 134, 268, 134 neurons, ReLU activation, 0.3 dropout).
*   **Support Vector Machine (SVM):** RBF kernel with C=10 performed very well, reaching **99.03%** accuracy on an undersampled dataset (45k samples).
*   **Hidden Markov Model (HMM):** Achieved **94.97%** accuracy using the full 67 features.
*   **GMM / GMM-UBM:** Showed lower performance (59% / 44%), struggling particularly with languages having similar acoustic features.

## Key Learnings & Challenges

*   Feature engineering (especially MFCCs and spectral features) is crucial.
*   MLP and SVM models proved highly effective for this task.
*   Hyperparameter tuning significantly impacts performance.
*   Distinguishing acoustically similar languages remains challenging, especially for GMM/HMM.
*   Data imbalance and computational cost were notable challenges.

## Dependencies

*   `librosa`
*   `scikit-learn`
*   `numpy`
*   `pandas`

## Authors

*   Ritika Thakur (2022408)
*   Saksham Singh (2022434)
*   Sarthak Gupta (2022451)
*   Sidhartha Garg (2022499)
```

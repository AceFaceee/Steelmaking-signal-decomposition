# Continuous Casting Process: Feature Extraction and Anomaly Detection


## Introduction

This project is focused on analyzing a time-series signal using the Hilbert-Huang Transform (HHT), a method particularly effective for non-stationary and nonlinear data. The primary goal is to uncover the dynamic frequency content of the signal, providing deeper insights into its underlying structure. This README details the motivation, methods, steps taken throughout the analysis, and insights gained.

## Motivation

Traditional Fourier-based methods often fall short when dealing with signals where frequency content varies over time. Such non-stationary signals require advanced techniques to accurately capture and analyze their dynamic nature. The Hilbert-Huang Transform (HHT), combining Empirical Mode Decomposition (EMD) with the Hilbert Transform, offers a robust framework for this purpose. Our motivation is to leverage HHT to gain a clearer understanding of the signal’s underlying characteristics.

## Methods

### 1. Signal Segmentation
   - **Objective**: Break down the entire signal into manageable parts for detailed analysis.
   - **Approach**: The signal was divided into 128-second segments. This duration was selected to balance between capturing essential features and preventing the visualizations from becoming overly complex.

### 2. Empirical Mode Decomposition (EMD)
   - **Objective**: Decompose the signal into simpler oscillatory components called Intrinsic Mode Functions (IMFs).
   - **Approach**: EMD was applied to each segment to extract IMFs, which represent the intrinsic oscillatory modes within the signal.

### 3. Hilbert Transform
   - **Objective**: Analyze the frequency content of each IMF.
   - **Approach**: The Hilbert Transform was applied to each IMF to obtain instantaneous amplitude and frequency, providing a time-frequency representation of the signal.

### 4. Time-Frequency-Amplitude (TFA) Visualization
   - **Objective**: Visualize the relationship between time, frequency, and amplitude.
   - **Approach**: For each segment, a scatter plot was created where the x-axis represents time, the y-axis represents instantaneous frequency, and the color intensity represents amplitude. This TFA visualization was compared side-by-side with the original signal to highlight how the frequency content evolves over time.

## Steps

1. **Data Preprocessing**:
    - Load and clean the time-series signal.
    - Segment the signal into 128-second intervals.

2. **Signal Decomposition**:
    - Apply EMD to each segment to decompose the signal into IMFs.

3. **Frequency Analysis**:
    - Perform the Hilbert Transform on each IMF to extract instantaneous frequency and amplitude.

4. **Visualization**:
    - Create side-by-side plots of the original signal segment and the TFA visualization for each segment.

## Insights

- **Dynamic Frequency Analysis**: The use of HHT provided detailed insights into how the signal’s frequency content changes over time, which is not possible with traditional methods.
- **Feature Identification**: The TFA visualizations highlighted key frequency components and their evolution, offering a clearer understanding of the signal’s underlying structure.
- **Enhanced Interpretation**: By comparing the original signal with the TFA visualizations, we could directly observe how specific features in the signal relate to changes in frequency content.

## Files

- `signal_analysis.py`: Python script containing the code for the entire analysis.
- `signal_data.csv`: Example dataset used for the analysis.
- `README.md`: This file, explaining the project’s background, methods, and insights.


## Conclusion

This project demonstrates the effectiveness of the Hilbert-Huang Transform in analyzing non-stationary signals. By breaking down the signal into IMFs and analyzing their frequency content, we gain valuable insights into the dynamic nature of the signal, which are not easily captured by traditional Fourier methods.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Acknowledgments
Thanks to the `Baosteel R%D Department` for sharing the datasets. Special thanks to Dr. Yu Yan (Baosteel Co.), Dr. He Fei(Hefei University of Technology) for mentoring.

Special thanks to the contributors of the `PyHHT` and `PyEMD` libraries for providing tools that made this analysis possible.


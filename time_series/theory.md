Detecting a correlation between two time series signals, especially when the correlation is not present at the beginning but emerges over time, involves several steps and techniques. Below is a comprehensive guide on how to approach this situation, including specific methods and tools.

### Steps to Detect Emerging Correlation in Time Series Signals

1. **Data Preprocessing**:
   - **Normalization**: Normalize the data to ensure both signals are on the same scale, which is crucial for correlation analysis.
   - **Handling Missing Values**: Fill or interpolate any missing values in the time series to avoid gaps in the data.

2. **Visual Inspection**:
   - **Plotting the Time Series**: Start by plotting both time series on the same graph to visually inspect any apparent relationships over time.
   - **Rolling Correlation**: Calculate a rolling correlation using a window to visualize how the correlation changes over time.

3. **Statistical Methods**:
   - **Pearson Correlation Coefficient**: Calculate the Pearson correlation coefficient over different time intervals to see if the correlation changes.
   - **Spearman Rank Correlation**: If the relationship is not linear, you might also consider calculating Spearman's rank correlation.

4. **Dynamic Time Warping (DTW)**:
   - **DTW Analysis**: This technique measures the similarity between two time series that may vary in speed. It can help identify shifts in the time series and when correlations begin to appear.

5. **Lag Analysis**:
   - **Cross-Correlation Function (CCF)**: Compute the cross-correlation between the two signals with various time lags. This helps in identifying if changes in one signal precede or follow changes in the other.
   - **Autocorrelation**: Analyze the autocorrelation of each signal to understand their internal dynamics.

6. **Machine Learning Approaches**:
   - **Granger Causality Test**: This statistical test can determine if one time series can predict another. If a change in the first signal precedes a change in the second signal, it suggests a causal relationship.
   - **Regression Models**: Fit regression models to determine if changes in one antenna's direction (predictor) lead to changes in the second antenna's signal (response).

7. **Feature Engineering**:
   - **Lagged Features**: Create lagged features of the first signal to analyze how past values affect the current state of the second signal.
   - **Differencing**: Use differencing to stabilize the mean of the time series, which can help in understanding relationships better.

8. **Change Point Detection**:
   - **Change Point Analysis**: Use techniques such as CUSUM or Bayesian change point detection to identify points in time where the statistical properties of the time series change. This could indicate a shift in correlation.

9. **Use of Advanced Time Series Models**:
   - **Vector Autoregression (VAR)**: A multivariate time series model that can capture linear relationships between multiple time series.
   - **Long Short-Term Memory (LSTM)**: If the relationship is complex and nonlinear, LSTM networks can capture temporal dependencies in time series data.

### Example Code: Rolling Correlation

Here is a Python code snippet using Pandas to compute the rolling correlation between two time series:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Generate synthetic time series data
np.random.seed(42)
time = pd.date_range(start='2023-01-01', periods=100)
signal1 = np.random.rand(100).cumsum()  # Simulate antenna 1 signal
signal2 = np.random.rand(100).cumsum()  # Simulate antenna 2 signal

# Introduce a correlation after a certain point
signal2[50:] += signal1[50:] * 0.5  # Make signal2 depend on signal1 after index 50

# Create DataFrame
df = pd.DataFrame({'Signal1': signal1, 'Signal2': signal2}, index=time)

# Calculate rolling correlation
rolling_correlation = df['Signal1'].rolling(window=10).corr(df['Signal2'])

# Plotting
plt.figure(figsize=(14, 7))
plt.plot(df['Signal1'], label='Signal 1', color='blue')
plt.plot(df['Signal2'], label='Signal 2', color='orange')
plt.plot(rolling_correlation, label='Rolling Correlation', color='green')
plt.title('Time Series Signals and Their Rolling Correlation')
plt.xlabel('Date')
plt.ylabel('Values')
plt.axvline(x=df.index[50], color='red', linestyle='--', label='Change Point')
plt.legend()
plt.show()
```

### Interpretation of the Results

- **Visual Plots**: The plotted signals help identify when they start to move together.
- **Rolling Correlation**: The rolling correlation plot will show changes in correlation over time. Before the change point (index 50), the correlation should be low, and after the change point, it should increase.

By following these steps, you can effectively identify and analyze the emerging correlation between two time series signals, especially in scenarios where one signal influences the other over time.
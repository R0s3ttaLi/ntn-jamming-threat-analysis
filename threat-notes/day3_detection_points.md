## Three potential points for anomalous observations:

The anomaly detection mechanisms are mostly applied in the physical layer or link layer. Few advanced jamming techniques exploit protocol properties.

* **Signal magnitude**: To effectively spoof legitimate signals, the interfering signals must have greater strength to successfully overpower them. A receiver should flag a signal source as potentially illegitimate if it detects a signal that is significantly stronger than expected.   
  Pros: Simple, fast, low cost, intuitive  
  Cons: Affected by environment and transceiver equipment
* **SNR value**: A substantial decrease in the Signal-to-Noise Ratio (SNR) below the typical range suggests potential jamming, specifically if the attacker is employing a noise-based technique.  
  Pros: Simple, fast, low cost, intuitive, sensitive to noise jamming  
  Cons: Not sensitive to spoofing / matched-signal / smart jamming. Affected by multi-path, obstacles, and weather.  
* **Spectrum**: Patterns of jamming can be observed in the frequency domain.  
  Pros: Spectrum preserves more information for jamming detection  
  Cons: Requires more data and computation power, different equipment needs calibration and normalization

---

Therefore, we can construct a two-layer framework for jamming detection.

Layer 0：Health & sanity checks (fast, low cost, continuos)  
RSSI / AGC behavior, SNR, lock time, loss-of-lock rate

Layer 1：Spectral / time-frequency inspection (slow, precise, ad hoc)  
PSD, spectrogram, occupied bandwidth, spectral flatness, peak density, periodicity, chirp/sweep patterns

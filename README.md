# Adaptive-Histogram-Equalization
Implementation of global and adaptive histogram equalization (tiling and sliding window) for grayscale image contrast enhancement, including visual comparisons and quantitative metrics (Entropy, PSNR).

---

This project implements **Global** and **Adaptive Histogram Equalization (AHE)** methods including both **Tiling** and **Sliding Window** approaches to enhance grayscale image contrast. It analyses and compares performance using **Entropy** and **PSNR** metrics.

---

##  Methods Overview

1. **Global Histogram Equalization**
   - Applies equalization once on the entire image.
   - Provides basic contrast enhancement but may cause detail loss.

   **Figure 1:** Original vs. Global Equalized Image  
   <img width="794" height="394" alt="image" src="https://github.com/user-attachments/assets/63bea853-de83-4d80-8de3-423eedcdfe9f" />



2. **Adaptive Histogram Equalization (Tiling)**
   - Divides the image into small tiles and equalizes each block independently.
   - Improves local contrast but may create edges between tiles.

   **Figure 2:** Tiling Equalization with different tile sizes  
   <img width="794" height="394" alt="image" src="https://github.com/user-attachments/assets/f4da6367-dbf2-4771-a2cf-d5be48754ad4" />


3. **Adaptive Histogram Equalization (Sliding Window)**
   - Uses a moving window to locally equalize contrast across the image.
   - Produces smoother transitions and better edge preservation.

   **Figure 3:** Sliding Equalization with different window sizes  
   <img width="950" height="315" alt="image" src="https://github.com/user-attachments/assets/eb527898-10ab-4276-a3e9-11b3c03bbbe3" />


---

##  Quantitative Analysis

Two metrics were used to evaluate the methods:

- **Entropy** → Measures the amount of information and contrast.  
- **PSNR (Peak Signal-to-Noise Ratio)** → Measures image quality compared to the original.

**Figure 4:** Entropy and PSNR comparison for Tiling and Sliding methods  
<img width="1189" height="490" alt="image" src="https://github.com/user-attachments/assets/a739d48c-6c5c-4e4c-8da5-fa0329a66e6d" />



| Method | Entropy | PSNR (dB) |
|:------------------|:---------:|:----------:|
| Global | 7.0106 | 27.78 |
| Tiling 16×16 | 7.9873 | 27.85 |
| Tiling 32×32 | 7.9807 | 27.82 |
| Tiling 64×64 | 7.9545 | 27.82 |
| Sliding 16×16 | 7.9697 | 27.85 |
| Sliding 32×32 | 7.9759 | 27.87 |
| Sliding 64×64 | 7.9754 | 27.86 |

---

##  Final Visual Comparison

**Figure 5:** Comparison between Global Equalization, Best Tiling (32×32), and Best Sliding (32×32).  
<img width="1415" height="452" alt="image" src="https://github.com/user-attachments/assets/00918b9f-66ee-4028-a6b8-0c0775bbf514" />



---

##  Code Structure

- Implemented in **Python (OpenCV, NumPy, Matplotlib, Pandas)**  
- Includes custom functions for:
  - `global_hist_equalization()`
  - `adaptive_hist_equalization_tiling()`
  - `adaptive_hist_equalization_sliding()`
  - `entropy()` and `psnr()`

---

##  Requirements

Install dependencies using:
```bash
pip install -r requirements.txt
```
---

## Results Summary
Adaptive methods (especially Sliding 32×32) achieved higher Entropy and slightly better PSNR than the Global approach.
The results confirm that adaptive equalization yields better local contrast with minimal noise.


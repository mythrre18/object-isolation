# Removing Partial / Overlapping Insect Fragments Using Connected Components

This repository provides a simple yet effective script to **clean ROI images** by removing small, disconnected insect fragments. These fragments are typically caused by **overlapping bounding boxes** created during dataset labeling or extraction.

The goal is to **preserve only the largest (complete) insect** in each image and whiten out all other components.

---

##  How It Works

The script performs the following steps:

1. **Convert the ROI image to grayscale**  
   Simplifies pixel intensity processing.

2. **Apply binary inverse thresholding**  
   Extracts dark insect regions from the bright background.

3. **Run connected components analysis**  
   Identifies all isolated pixel groups within the image.

4. **Select the largest component**  
   Assumes it represents the dominant, complete insect.

5. **Whiten all smaller components**  
   Removes partial, noisy, or overlapping insect fragments.

---

##  Why This Is Useful

Bounding-box cropped datasets often contain:

- Partial insect bodies  
- Overlapping fragments from nearby insects  
- Noisy disconnected blobs  

Such artifacts negatively affect model training by introducing:

- False visual features  
- Incorrect labels  
- Inconsistent patterns  

Cleaning these images ensures **higher quality training data**, improving:

- Classification accuracy  
- Detection robustness  
- Feature learning consistency  

---

##  Example Processing Pipeline

Input ROI
→ Thresholding
→ Connected Components
→ Keep Largest Component
→ Output Clean ROI


Only the main insect remains; all smaller pieces are removed.
<img width="969" height="367" alt="Screenshot 2025-11-23 210231" src="https://github.com/user-attachments/assets/22880de6-0827-4aab-941e-8ae50c0586d2" />

---

##  Ideal For

✔ Insect ROI dataset cleanup  
✔ ML/DL preprocessing pipelines  
✔ Removing bounding-box artifacts  
✔ Preparing data for classification or detection models  

---

##  Script Overview

The script uses:

- **OpenCV** — thresholding & connected components  
- **NumPy** — array operations  
- Simple image preprocessing logic to isolate the main insect

You can easily integrate it into any dataset pipeline.





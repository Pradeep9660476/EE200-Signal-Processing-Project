# EE200 Signal & Image Processing Project

**Course:** EE200 – Signals, Systems, and Networks
**Author:** Pradeep Meena (Roll No. 240757)
**Instructor:** Dr. Tushar Sandhan

This project applies Fourier-transform-based signal processing to two problems: blending two images in the frequency domain to create a perceptual illusion, and removing an unwanted sound from an audio track using frequency filtering. Both tasks are implemented in Python.

---

## Q1 — Frequency Mixer: "Beauty and the Blur"

A **hybrid image** that is perceived differently depending on viewing distance — a cat when seen up close, and a dog when seen from far away.

**How it works:**
- Applied the **2D Discrete Fourier Transform (FFT)** to grayscale cat and dog images.
- Extracted **high-frequency** content (fine detail, edges) from the cat and **low-frequency** content (overall structure) from the dog.
- Fused the two frequency components and applied the **inverse FFT** to reconstruct the hybrid image.
- Also analyzed the magnitude spectrum and verified that rotating an image rotates its frequency spectrum.

**Key concept:** Low frequencies carry the broad shape of an image, while high frequencies carry the sharp details. By mixing them, the brain reads the result differently at different distances.

## Q2 — Frequency De-mixer: "Unwanted Solo"

Removes an unwanted instrumental beat from a music track to restore the original audio.

**How it works:**
- Analyzed the input audio in the time domain and via **Power Spectral Density (PSD)**.
- Identified the unwanted frequencies (≈ 1000–5000 Hz) and removed them using **FFT-based stopband filtering**.
- Designed a **10th-order Butterworth bandstop filter** with `scipy.signal` for a sharp cutoff.
- Validated results with time-domain, PSD, spectrogram, Bode-plot, and pole-zero comparisons of the original vs. filtered audio.

---

## Tech Stack
- **Python**
- **NumPy** – FFT and numerical processing
- **OpenCV (cv2)** – image loading and Gaussian blur
- **SciPy** – Butterworth filter design and signal analysis
- **Matplotlib** – visualizations and plots

## Repository Contents
| File | Description |
|------|-------------|
| `Q1_frequency_mixer.ipynb` | Notebook for the hybrid image task |
| `Q1_report.pdf` | Detailed report for Q1 |
| `Q2_frequency_demixer.ipynb` | Notebook for the audio filtering task |
| `Q2_report.pdf` | Detailed report for Q2 |
| `cat.jpg`, `dog.jpg` | Input images for Q1 |
| `input_audio.wav` | Original audio for Q2 |
| `output_filtered_audio.wav` | Filtered audio output for Q2 |

## How to Run
1. Install the dependencies:
   ```bash
   pip install numpy opencv-python scipy matplotlib
   ```
2. Open either notebook in Jupyter:
   ```bash
   jupyter notebook
   ```
3. Run all cells. Make sure the input images / audio file are in the same folder as the notebook.

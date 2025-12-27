# Spectral Filter (Basic FFT Version)

This repository contains a **minimal real-time spectral filter** implemented in Python.

The goal of this project is **educational**, not technical perfection:
it demonstrates, as explicitly as possible, how **FFT-based filtering works** by
directly manipulating frequency-domain bins.

There is **no windowing** and **no overlap–add** on purpose.

---

## What this project does

- Takes **real-time audio input**
- Processes audio in **blocks**
- Computes an **FFT** for each block
- **Keeps or discards frequency bins** based on a simple rule
- Converts the signal back to the time domain
- Outputs audio in real time

Filtering is implemented by:

- looping over bins
- computing their frequency
- deciding whether to keep or discard them

There are **no filter coefficients**, no IIR/FIR design.

---

##  Use

- Route audio from a DAW or microphone into the script
- Listen to how removing frequency bands affects the sound
- Change cutoff frequencies
- Experiment with different FFT sizes
- Observe how artifacts change with parameters


---

## Requirements

- Python 3.9+
- NumPy
- sounddevice
- An audio interface or virtual audio device

Install dependencies:

```bash
git clone https://github.com/iorobertob/spectral-filter.git
cd spectral-filter
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
# complete the code in spectral_filter.py (read pdf for instructions)
python spectral_filter.py

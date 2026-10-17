# Signal And Image Processing

Personal learning repository: Jupyter notebooks with Python (NumPy, SciPy, Matplotlib) exercises on digital signal processing, built up step by step from signal basics to the Fourier Transform. Some comments and notes inside the notebooks are in Polish.

## Contents

| Folder | Notebook | Topic |
|---|---|---|
| `Fundamentals_SignalProcessing` | `ContinuousTimeSignals.ipynb` | Unit impulse, step and ramp, time-shifted signals, sinusoidal and exponential signals (including `scipy.signal.unit_impulse`) |
| | `DiscreteTimeSignal.ipynb` | Discrete-time versions of impulse, sinusoidal and exponential signals |
| | `ADConversion.ipynb` | Analog-to-digital conversion: sampling and quantization |
| | `Sampling_and_Reconstruction.ipynb` | Nyquist criterion: bad (`fs < 2·Fmax`) vs. good (`fs ≥ 2·Fmax`) sampling |
| `Convolution` | `Convolution_Sum.ipynb` | Convolution step by step: zero padding, flipped kernel, for-loop implementation |
| | `Convolution(splot).ipynb` | `np.convolve` (`full` / `same` modes), denoising and edge detection with convolution, the convolution theorem (time vs. frequency domain via `scipy.fft`) |
| `Denoising` | `Moving_Avarage_Filter.ipynb` | Denoising with a moving average filter |
| | `Gaussian_Mean_Filter.ipynb` | Gaussian kernel (FWHM) filter, zero padding |
| | `Median_Filter.ipynb` | Median filter |
| | `Removing_noise_spikes.ipynb` | Removing spikes from `Spike.csv` with thresholding (`np.where`) and a median filter |
| `FourierTransform` | `ComplexNumbers.ipynb` | Complex numbers: plotting on the complex plane, arithmetic, conjugate, magnitude, angle, complex sine wave |
| | `GeneratingWaves.ipynb` | Combining sine and cosine waves and a DC component |
| | `FourierTransform.ipynb` | Fourier Transform implemented from scratch (dot product of the signal with complex sine waves) and plotted next to the signal |

## Setup

Requirements: Python 3 with `numpy`, `scipy`, `pandas`, `matplotlib` and `jupyter`.

```bash
# conda (Convolution/ and Denoising/ ship an environment.yml)
conda env create -f Denoising/environment.yml   # edit the `name`/`prefix` lines to a path on your machine first

# or pip
pip install numpy scipy pandas matplotlib jupyter
```

Then start Jupyter from the repository root and open any notebook:

```bash
jupyter lab
```

`Denoising/Removing_noise_spikes.ipynb` reads `Spike.csv` and `Convolution/Convolution(splot).ipynb` reads `convolution.png` using relative paths, so run these notebooks with their own folder as the working directory (Jupyter does this by default).

## Repository layout

```
Convolution/                   convolution notebooks, convolution.png, environment.yml
Denoising/                     filtering notebooks, Spike.csv, environment.yml
FourierTransform/              complex numbers, waves, Fourier Transform
Fundamentals_SignalProcessing/ signals, sampling, A/D conversion, requirements.txt
```


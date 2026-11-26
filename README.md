# MPHY0058 Group Coursework – Heart Rate Estimation

Estimating heart rate from (A) an optical sensor signal and (B) a phone-camera video of a finger, using Python.

## Team
| Name | GitHub | Role |
|---|---|---|
| Haozhe Li | @lihaoZHew | Repository owner, Part A code |
| Lucas Xue | @Lucas-Xue | Part A code & report |
| Yanxi Xie | @Eden19697 | Part B – video loading & filtering |
| Shuming Zhang | @zsooogod | Part B – FFT, peak detection & summary |
| Xiaoan Shi | @SeanS1026 | Introduction, discussion, references |

## Project structure
- `heart_rate.ipynb` – all analysis code
- `report.docx` – written report
- `data/` – input data
- `figures/` – generated plots

## Getting the data
`video_of_finger.MOV` (118 MB) is larger than GitHub's 100 MB limit, so it is **not** in this repository.
Download it from Moodle and place it at `data/video_of_finger.MOV`.

## Environment
The results in the notebook and report were produced with:

| Package | Version |
|---|---|
| Python | 3.13.9 |
| numpy | 2.3.5 |
| pandas | 2.3.3 |
| scipy | 1.16.3 |
| matplotlib | 3.10.6 |
| opencv-python | 5.0.0.93 |

Install with:

```bash
pip install numpy==2.3.5 pandas==2.3.3 scipy==1.16.3 matplotlib==3.10.6 opencv-python==5.0.0.93 jupyter
```

The video is read with OpenCV's **FFmpeg** backend (`cv2.CAP_FFMPEG`), which the standard `opencv-python` wheels include. Different backends decode the same file to different grayscale values, so the notebook fixes the backend and prints its name and the OpenCV version in section B.1.

## How to run
1. Place `video_of_finger.MOV` in `data/` (see above).
2. Open `heart_rate.ipynb` and choose **Restart & Run All**. Part B reuses functions from Part A, so the cells must run in order.
3. Figures are written to `figures/` and numerical results to `data/` (`partA_*.csv`, `partB_*.csv`).

Expected results: Part A 55.1 bpm (FFT) and 55.5 bpm (peak intervals); Part B 71.9 bpm (FFT, 71.87) and 71.9 bpm (peak intervals, 71.95).

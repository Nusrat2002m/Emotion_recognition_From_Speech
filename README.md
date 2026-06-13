# Emotion_recognition_From_Speech

## Files

| File | Task | Dataset | Models |
|---|---|---|---|
| `task2_emotion_recognition.py` | Emotion Recognition from Speech | RAVDESS (real, if you provide audio) / synthetic MFCC fallback | MLP (Neural Network) on MFCC features |

## How to run

Each script is self-contained:

```bash
python3 Emotion_recognition_From_Speech.py
```

All required libraries (`numpy`, `pandas`, `scikit-learn`, `matplotlib`)
are standard and install with:

```bash
pip install numpy pandas scikit-learn matplotlib
```

## Important honesty notes (please read before submitting)

**Task 2 (Emotion Recognition from Speech):** This environment had no
   internet access to download RAVDESS/TESS/EMO-DB and no audio files
   were uploaded. The script is written to:
   - **Automatically use real audio** if you place `.wav` files from
     RAVDESS into a `speech_dataset/` folder (it will extract real MFCCs
     with `librosa` and train on real data — this is what you should run
     before final submission).
   - **Fall back to a synthetic MFCC dataset** otherwise, so the full
     pipeline (feature extraction → scaling → neural network → evaluation)
     is demonstrated end-to-end. The 100% accuracy you'll see in this run
     is from the synthetic fallback (the classes are cleanly separable by
     design) — **not a result on real speech data**. Download RAVDESS
     (link is in the script's comments, ~1GB, free) and re-run for genuine
     results.


## Results summary (from the runs in this environment)

- **Speech Emotion:** Pipeline verified end-to-end on synthetic
  data (100% accuracy as expected for cleanly-separable synthetic
  classes). **Re-run with real RAVDESS audio before submitting** to get
  genuine numbers — real-world speech emotion accuracy is typically in
  the 60–80% range, which is normal and expected.


## Risks / limitations to be aware of

- Synthetic data (Tasks 2 fallback) can make models look better than
  they would on real-world data — don't present synthetic results as if
  they came from real datasets.

- All accuracy numbers will vary slightly between runs unless random
  seeds are fixed (they are, here, via `random_state=42`).

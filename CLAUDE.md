# Introduction to Probability — Python Notebooks

## Project

Blitzstein & Hwang, *Introduction to Probability* (2nd ed., Chapman & Hall/CRC).

Each chapter ends with an R section (§X.8 or similar) that illustrates probability concepts via simulation and computation. The goal of this project is to produce a Jupyter notebook for each chapter that re-implements those ideas in Python — written in the same expository style as the original, not as a comparison to R.

## Environment

- **Python**: `C:\Users\Alexe\anaconda3\python.exe` (Anaconda install; `python-docx` is installed)
- **Read a `.docx`**: The `.docx` may be locked if open in Word. Always copy it first, then read via a temp script:
  1. `Copy-Item "c:\Users\Alexe\OneDrive\Yura - College\Geo\introduction-to-probability\chN.docx" "$env:TEMP\chN_copy.docx" -Force`
  2. Write a script to `$env:TEMP\read_chN.py` with `sys.stdout.reconfigure(encoding='utf-8')` to handle Unicode, then run:  
     `& "C:\Users\Alexe\anaconda3\python.exe" "$env:TEMP\read_chN.py" | Out-File "$env:TEMP\chN_text.txt" -Encoding utf8`
- **Execute a notebook**: `& "C:\Users\Alexe\anaconda3\python.exe" -m jupyter nbconvert --to notebook --execute --inplace chN_python.ipynb`

## Workflow per chapter

1. The source material arrives as a `.docx` file (e.g. `ch2.docx`) containing the R section of that chapter.
2. Produce a notebook `chN_python.ipynb` that covers the same concepts and examples in Python.
3. Execute the notebook to verify all cells run without errors before committing.
4. Commit `chN.docx` and `chN_python.ipynb` together.

## Notebook conventions

- **Style**: prose-first, same voice as the textbook. Explain what the code does in markdown cells, then show the code. No R-vs-Python comparison frames.
- **Copyright**: do not copy sentences from the source word-for-word. Restate and paraphrase all explanatory prose; only the mathematical logic of code examples may closely mirror the originals.
- **Libraries**: `numpy` (arrays, simulation), `scipy.stats` (distributions — PMF, CDF, etc.), `scipy.special` (special functions such as `comb`), `seaborn` (plots), `matplotlib.pyplot` (figure/axes creation), `math` (exact integer arithmetic). Import only libraries that are actually used in the notebook.
- **Plotting**: use **seaborn** for all plot calls. `matplotlib.pyplot` is imported as `plt` and used only for `plt.subplots()`, `plt.tight_layout()`, and `plt.show()` — never for direct plot calls. Call `sns.set_theme(palette="deep")` once in the imports cell; do not hardcode colours in individual plot calls.
- **Random generator**: create once as `rng = np.random.default_rng(seed=42)` and reuse.
- **Indexing note**: mention 0-based indexing naturally where it matters, without framing it as a difference from R.
- **Replicate idiom**: list comprehensions `[expr for _ in range(N)]` are the standard way to repeat a random experiment N times.
- **Sequences**: `np.arange(1, n+1)` for the integer sequence 1..n.
- **Cell IDs**: include `"id"` fields on every cell (nbformat 5.1 requirement).

## Files

| File | Description |
|------|-------------|
| `ch1.docx` | Ch. 1 R section (source) |
| `ch1_python.ipynb` | Ch. 1 Python notebook |
| `ch2.docx` | Ch. 2 R section (source) |
| `ch2_python.ipynb` | Ch. 2 Python notebook |
| `ch3.docx` | Ch. 3 R section (source) |
| `ch3_python.ipynb` | Ch. 3 Python notebook |
| `ch4.docx` | Ch. 4 R section (source) |
| `ch4_python.ipynb` | Ch. 4 Python notebook |
| `ch5.docx` | Ch. 5 R section (source) |
| `ch5_python.ipynb` | Ch. 5 Python notebook |

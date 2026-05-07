# Introduction to Probability — Python Notebooks

## Project

Blitzstein & Hwang, *Introduction to Probability* (2nd ed., Chapman & Hall/CRC).

Each chapter ends with an R section (§X.8 or similar) that illustrates probability concepts via simulation and computation. The goal of this project is to produce a Jupyter notebook for each chapter that re-implements those ideas in Python — written in the same expository style as the original, not as a comparison to R.

## Workflow per chapter

1. The source material arrives as a `.docx` file (e.g. `ch2.docx`) containing the R section of that chapter.
2. Produce a notebook `chN_python.ipynb` that covers the same concepts and examples in Python.
3. Execute the notebook to verify all cells run without errors before committing.
4. Commit `chN.docx` and `chN_python.ipynb` together.

## Notebook conventions

- **Style**: prose-first, same voice as the textbook. Explain what the code does in markdown cells, then show the code. No R-vs-Python comparison frames.
- **Libraries**: `numpy` (arrays, simulation), `scipy.special` (special functions), `matplotlib.pyplot` (plots), `math` (exact integer arithmetic). Import all at the top.
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

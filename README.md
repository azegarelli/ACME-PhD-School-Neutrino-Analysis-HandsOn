# Neutrino Astronomy — PhD School Hands-on

Two hands-on Jupyter exercises accompanying the lecture **Analysis Techniques in Neutrino Astronomy**:

| Exercise | Student notebook | Instructor solutions |
| --- | --- | --- |
| IceCube HESE public data: MC/data comparisons, flux weights, expected counts, effective area, migration matrices | `01_HESE_student.ipynb` | `01_HESE_solutions.ipynb` |
| Toy Monte Carlo: generate with an artificial spectrum, reweight to physical hypotheses, study detector response | `02_Toy_MC_student.ipynb` | `02_Toy_MC_solutions.ipynb` |

The **student** notebooks include TODOs and conceptual questions. The **solutions** notebooks contain worked code and explanations. 
**Solutions will be released after the hands-on session**.

## Requirements

- Python **3.10 or newer** (Python 3.11 or 3.12 recommended).
- Internet access for the initial Python-package installation and for the public IceCube HESE dataset download. The toy MC notebook does not need a data download.
- About **75 MB** for the IceCube ZIP, plus space for the extracted JSON files.

Required packages are listed in [`requirements.txt`](requirements.txt): `numpy`, `pandas`, `matplotlib`, `jupyterlab`, and `ipykernel`. The remaining imports (`json`, `pathlib`, `urllib`, `zipfile`, `shutil`) are part of Python's standard library.

## Installation using a virtual environment (recommended)

**1. Download or clone this repository**, then open a terminal in the folder containing `requirements.txt`.

**2. Create a Python virtual environment:**

```bash
python -m venv .venv
```

On systems where `python` is not the desired Python 3 interpreter, use `python3` or `py -3` for this step.

**3. Activate it:**

On **macOS / Linux**:

```bash
source .venv/bin/activate
```

On **Windows PowerShell**:

```powershell
.\.venv\Scripts\Activate.ps1
```

On **Windows Command Prompt**:

```cmd
.venv\Scripts\activate.bat
```

**4. Install the dependencies:**

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

**5. Launch JupyterLab:**

```bash
jupyter lab
```

Open `01_HESE_student.ipynb` or `02_Toy_MC_student.ipynb` in JupyterLab. Select the Python kernel associated with your `.venv` environment (usually detected automatically when JupyterLab is launched from the activated environment).

If your environment is **not** listed as a kernel, while the environment is activated run:

```bash
python -m ipykernel install --user --name neutrino-hands-on --display-name "Python (Neutrino Hands-on)"
```

Then choose **Python (Neutrino Hands-on)** in the notebook's kernel menu.

**6. When finished**, stop JupyterLab with `Ctrl+C` in the terminal. Optionally leave the virtual environment:

```bash
deactivate
```

## HESE public dataset

`01_HESE_student.ipynb` and `01_HESE_solutions.ipynb` use the **IceCube 7.5-year High-Energy Starting Events (HESE)** public data release. Their setup code:

1. Looks for previously extracted HESE JSON files.
2. Otherwise looks for a local `20211217_HESE-7-5-year-data.zip` archive.
3. Otherwise attempts to download the official archive from IceCube, then extracts the required JSON files into `HESE_7p5_data/`.

The download happens once, unless the files are removed. If it fails, download the archive manually from the [official HESE data release](https://icecube.wisc.edu/data-releases/2021/12/hese-7-5-year-data/) and save it **beside the notebook** with the name `20211217_HESE-7-5-year-data.zip`; rerun the setup cell. Alternatively, provide the four JSON files in `HESE_7p5_data/`: `HESE_data.json`, `HESE_mc_truth.json`, `HESE_mc_observable.json`, and `HESE_mc_flux.json`.

### References

- [IceCube HESE 7.5-year public data release](https://icecube.wisc.edu/data-releases/2021/12/hese-7-5-year-data/), DOI: [10.21234/4EQJ-BB17](https://doi.org/10.21234/4EQJ-BB17).
- [Official HESE data dictionary and MC weighting documentation](https://github.com/icecube/HESE-7-year-data-release).

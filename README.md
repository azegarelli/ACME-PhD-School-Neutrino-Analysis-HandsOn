# Analysis Techniques in Neutrino Astronomy

**PhD School — Teaching Materials**

Jupyter hands-on material accompanying the lecture **Analysis Techniques in Neutrino Astronomy**.

The **main hands-on** for the school is the IceCube HESE exercise. A second toy Monte Carlo exercise is provided **for optional self-study**; it is **not required** for the scheduled hands-on session.

| Status | Exercise | Notebook |
| --- | --- | --- |
| **Main hands-on** | IceCube HESE public data: MC/data comparisons, flux weights, expected counts, effective area, migration matrices | [`01_HESE_student.ipynb`](01_HESE_student.ipynb) |
| **Optional / extra practice** | Toy Monte Carlo: event generation, reweighting to physical spectra, and detector response | [`02_Toy_MC_student.ipynb`](optional/02_Toy_MC_student.ipynb) |

**The solutions will be uploaded to this repository after the hands-on session.**

**Start with `01_HESE_student.ipynb`.**

The notebooks contain coding exercises and conceptual questions. Run the cells in order.

## Requirements

- Python **3.10 or newer** (Python 3.11 or 3.12 recommended).
- Internet access for the initial Python-package installation and for the public IceCube HESE dataset download. The optional toy MC notebook does not need a data download.
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

For the scheduled hands-on, open **`01_HESE_student.ipynb`** from the repository root. If you would like additional practice later, open **`optional/02_Toy_MC_student.ipynb`** instead. Select the Python kernel associated with your `.venv` environment (usually detected automatically when JupyterLab is launched from the activated environment).

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

The `01_HESE_student.ipynb` notebook uses the **IceCube 7.5-year High-Energy Starting Events (HESE)** public data release.

The notebook automatically downloads the dataset from the official IceCube repository and extracts the required files into `HESE_7p5_data/`. The download is performed only once, unless the files are removed.

The dataset is also available from the [official HESE data release](https://icecube.wisc.edu/data-releases/2021/12/hese-7-5-year-data/).

**Do not upload the IceCube data archive or the extracted JSON files to GitHub** as part of this teaching repository; instead link to and cite the official public release.

## References

- [IceCube HESE 7.5-year public data release](https://icecube.wisc.edu/data-releases/2021/12/hese-7-5-year-data/), DOI: [10.21234/4EQJ-BB17](https://doi.org/10.21234/4EQJ-BB17).
- [Official HESE data dictionary and MC weighting documentation](https://github.com/icecube/HESE-7-year-data-release).

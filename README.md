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

## Getting started

### Option 1 — Run online with Binder (recommended)

You can run the hands-on directly in your browser without installing anything locally.

Click the **Launch Binder** button below to open the Jupyter environment.

[![Launch Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/USERNAME/REPOSITORY/HEAD?urlpath=lab/tree/01_HESE_student.ipynb)

**Important:** Binder sessions are temporary. Remember to download your completed notebook to save your work.

### Option 2 — Run locally

Alternatively, you can run the exercises on your own computer.

**Download ZIP**

1. Click the green **Code** button on this GitHub repository.
2. Select **Download ZIP**.
3. Extract the ZIP file to a folder on your computer.
4. Open a terminal in the extracted folder.

**Clone with Git**

If you have Git installed, open a terminal and run:

```bash
git clone https://github.com/azegarelli/ACME-PhD-School-Neutrino-Analysis-HandsOn.git
cd ACME-PhD-School-Neutrino-Analysis-HandsOn
```

Once inside the project folder, follow the requirements and installation instructions below.

## Requirements

- Python **3.10 or newer** (Python 3.11 or 3.12 recommended).
- Internet access for the initial Python-package installation and for the public IceCube HESE dataset download. The optional toy MC notebook does not need a data download.
- About **75 MB** for the IceCube ZIP, plus space for the extracted JSON files.

Required packages are listed in [`requirements.txt`](requirements.txt).

## Local installation using a virtual environment

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

## References

- [IceCube HESE 7.5-year public data release](https://icecube.wisc.edu/data-releases/2021/12/hese-7-5-year-data/), DOI: [10.21234/4EQJ-BB17](https://doi.org/10.21234/4EQJ-BB17).
- [Official HESE data dictionary and MC weighting documentation](https://github.com/icecube/HESE-7-year-data-release).

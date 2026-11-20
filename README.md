# Neutrino Astronomy — PhD School Hands-on

Jupyter hands-on material accompanying the lecture **Analysis Techniques in Neutrino Astronomy**.

The **main hands-on** for the school is the IceCube HESE exercise. A second, more advanced toy Monte Carlo exercise is provided **for optional self-study**; it is **not required** for the scheduled hands-on session.

| Status | Exercise | Student notebook | Instructor solutions |
| --- | --- | --- | --- |
| **Main hands-on** | IceCube HESE public data: MC/data comparisons, flux weights, expected counts, effective area, migration matrices | `01_HESE_student.ipynb` | `01_HESE_solutions.ipynb` |
| **Optional / extra practice** | Toy Monte Carlo: generate with an artificial spectrum, reweight to physical hypotheses, study detector response | `optional/02_Toy_MC_student.ipynb` | `optional/02_Toy_MC_solutions.ipynb` |

**Start with `01_HESE_student.ipynb`.** There is no need to complete the optional toy MC exercise during the school session. Student notebooks contain TODOs and conceptual questions; instructor solution notebooks contain worked code and explanations. Run notebook cells in order.

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

`01_HESE_student.ipynb` and `01_HESE_solutions.ipynb` use the **IceCube 7.5-year High-Energy Starting Events (HESE)** public data release. Their setup code:

1. Looks for previously extracted HESE JSON files.
2. Otherwise looks for a local `20211217_HESE-7-5-year-data.zip` archive.
3. Otherwise attempts to download the official archive from IceCube, then extracts the required JSON files into `HESE_7p5_data/`.

The download happens once, unless the files are removed. If it fails, download the archive manually from the [official HESE data release](https://icecube.wisc.edu/data-releases/2021/12/hese-7-5-year-data/) and save it **beside the notebook** with the name `20211217_HESE-7-5-year-data.zip`; rerun the setup cell. Alternatively, provide the four JSON files in `HESE_7p5_data/`: `HESE_data.json`, `HESE_mc_truth.json`, `HESE_mc_observable.json`, and `HESE_mc_flux.json`.

**Do not upload the IceCube data archive or the extracted JSON files to GitHub** as part of this teaching repository; instead link to and cite the official public release.

## Scientific notes

- `weightOverFluxOverLivetime` is the normalized *neutrino* MC weight before multiplying by the assumed physical flux and observation time; inspect its documented units before computing expected event counts.
- Atmospheric-muon weights use `muonWeightOverLivetime`, not the neutrino flux weighting formula.
- The HESE release supports selected-event energy/zenith response and effective area derived from the normalization weights, but not a full 3D point-spread function when true/reconstructed azimuths are not provided.
- The reconstructed deposited energy is **not** the same quantity as the true neutrino energy.
- These are educational exercises, not a reproduction of the full HESE likelihood analysis.

## Troubleshooting

- **`ModuleNotFoundError`**: check that Jupyter is using the `.venv` kernel; re-run `python -m pip install -r requirements.txt` from the activated environment.
- **Dataset download unavailable**: use the manual-download instructions above.
- **LaTeX formulas not visible**: make sure the cell type is *Markdown* and execute that cell with `Shift+Enter`.
- **PowerShell blocks activation**: use Command Prompt with `.venv\Scripts\activate.bat`, or consult your institution's PowerShell execution policy; no administrative privileges are needed for `venv`.

## References

- [IceCube HESE 7.5-year public data release](https://icecube.wisc.edu/data-releases/2021/12/hese-7-5-year-data/), DOI: [10.21234/4EQJ-BB17](https://doi.org/10.21234/4EQJ-BB17).
- [Official HESE data dictionary and MC weighting documentation](https://github.com/icecube/HESE-7-year-data-release).

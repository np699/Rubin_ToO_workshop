# Rubin ToO Workshop Tutorial

This folder contains a guided Jupyter tutorial for simulating a single Rubin target-of-opportunity kilonova follow-up case.

## Start Here

Open `rubin_too_workshop.ipynb` and run the notebook from top to bottom. The notebook is structured as a workshop tutorial with setup notes, editable parameters, and two example runs:

- `100 Mpc`: baseline event distance
- `200 Mpc`: same event moved farther away

The notebook writes new products to `outputs/` so participants can rerun the tutorial without overwriting the provided example files.

## Files

- `rubin_too_workshop.ipynb`: main tutorial notebook
- `S251112cm_obs_vanilla.h5`: Rubin visit table used as the simulation input

## Create the Conda Environment

From this folder, run:

```bash
conda env create -f environment.yml
conda activate rubin-too-workshop
python -m ipykernel install --user --name rubin-too-workshop --display-name "Rubin ToO Workshop"
```

Then open `rubin_too_workshop.ipynb` and choose the `Rubin ToO Workshop` kernel.

The notebook sets `NUMBA_DISABLE_JIT=1` before importing `redback` to avoid Numba cache issues on workshop machines. It uses the Bulla BNS kilonova model through `redback-surrogates`, so the environment pins `numpy=1.26.4` for Torch/kilonovanet compatibility.

## Expected Python Packages

The tutorial expects a Python/Jupyter environment with:

- `numpy`
- `pandas`
- `matplotlib`
- `astropy`
- `lightcurvelynx`
- `redback`
- `tables` or another pandas-compatible HDF5 backend

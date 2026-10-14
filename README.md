# LABB – Tre i rad

A lab on knowledge-based AI agents for two-player games, played through tic-tac-toe. It runs entirely
in the browser with [JupyterLite](https://jupyterlite.readthedocs.io) and the Pyodide kernel, so
students do not need to install anything.

➡️ **https://mkewest.github.io/tre-i-rad/**

The site opens the lab notebook directly. It can also be opened in the simpler Notebook interface:
https://mkewest.github.io/tre-i-rad/notebooks/index.html?path=LABB_%20Tre%20i%20rad.ipynb

## Notes

- Changes students make are stored in their browser (IndexedDB), not on the server. To keep their
  work they should download the notebook (*File → Download*).
- A long-running cell cannot be interrupted in JupyterLite; use *Kernel → Restart Kernel* instead.

## Structure

- `content/` – the notebook served on the site
- `workspaces/default.jupyterlab-workspace` – opens the notebook when the site is first loaded
- `jupyter_lite_config.json` – build configuration (the Python packages for the kernel, via pyodide-lock)
- `requirements.txt` – the JupyterLite build dependencies
- `.github/workflows/deploy.yml` – builds the site and deploys it to GitHub Pages on pushes to `main`

## Building locally

```bash
python -m pip install -r requirements.txt
jupyter lite build --contents content --output-dir dist
jupyter lite serve --output-dir dist
```

Based on the [JupyterLite demo template](https://github.com/jupyterlite/demo).

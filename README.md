# Edito-Playground

Playground notebooks that demonstrate how to interact with the [EDITO data API](https://docs.dive.edito.eu/articles/integration/interactWithTheDataAPI.html): listing catalog collections, filtering items, and previewing assets with Xarray.

## Setup

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
pip install jupyterlab
```

Cartopy and Rasterio depend on GEOS/PROJ/GDAL. On macOS you can install them with Homebrew:

```bash
brew install geos proj gdal
```

## Configure credentials

Obtain a personal access token (client_id `edito`) and expose it before starting Jupyter. The notebooks look for `EDITO_API_TOKEN` first and fall back to `EDITO_ACCESS_TOKEN` so you can set whichever fits your workflow:

```bash
export EDITO_API_TOKEN=your_token_here  # or: export EDITO_ACCESS_TOKEN=...
```

Optional environment variables:

- `EDITO_DATA_BASE_URL` to target a non-production endpoint.
- `EDITO_DOWNLOAD_DIR` to override the default `data/` download directory.

## Launch the playground

```bash
jupyter lab
```

Open the notebooks under `notebooks/`:

1. `notebooks/01_catalog_explorer.ipynb` – list collections, inspect temporal/spatial metadata, and fetch sample items.
2. `notebooks/02_item_quicklook.ipynb` – parameterize STAC searches quickly and inspect the raw asset metadata for any result row.
3. `notebooks/03_provider_scanner.ipynb` – spotlight EMODnet vs CMEMS resources and verify whether specific CMEMS dataset IDs are exposed in the catalog.
4. `notebooks/04_stac_client_walkthrough.ipynb` – follow the PySTAC Client workflow to traverse catalogs and query CMEMS items programmatically.

Downloaded samples are stored under `data/` (gitignored except for the placeholder file).
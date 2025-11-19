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

Obtain a personal access token (client_id `edito`) and expose it before starting Jupyter:

```bash
export EDITO_API_TOKEN=your_token_here
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

Downloaded samples are stored under `data/` (gitignored except for the placeholder file).
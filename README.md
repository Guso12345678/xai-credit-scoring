# XAI aplicado a scoring de crédito

Proyecto final de Explainable AI (ICAI Comillas, 2026/27), Opción A. Modelo que predice el impago de clientes de tarjeta de crédito (dataset UCI Taiwan, 30.000 clientes) y que se explica con SHAP, permutation importance, PDP/ICE y LIME. Incluye sanity checks de las explicaciones, mejora del modelo, insights de negocio y auditoría de equidad.

## Estructura
- `notebooks/01_xai_credit_scoring.ipynb`: todo el análisis, de la carga de datos a las conclusiones.
- `data/`: el CSV se descarga solo la primera vez (ver `data/README.md` para el origen y los enlaces).
- `reports/figures/` y `reports/results.json`: figuras y números que genera el notebook.
- `requirements.txt`: dependencias.

## Cómo ejecutarlo
1. Crear entorno e instalar dependencias:
   `python -m venv venv`, activarlo e instalar con `pip install -r requirements.txt`
2. Abrir `notebooks/01_xai_credit_scoring.ipynb` (VS Code o JupyterLab) y ejecutar todas las celdas de arriba abajo. Tarda unos minutos.
3. Sin internet: descargar el CSV desde UCI (id 350) y guardarlo como `data/taiwan_default.csv`.

Semilla fija (`SEMILLA = 42`), así que los resultados se repiten.

## Datos
UCI Machine Learning Repository, *Default of Credit Card Clients* (id 350): https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients. Yeh & Lien (2009), *Expert Systems with Applications* 36(2).

## Limitaciones
Datos de Taiwán de 2005, un único corte temporal con split aleatorio y costes de decisión (FN:FP) que son un supuesto.

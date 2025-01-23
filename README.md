# vscode-extractor

## Introducción

`vscode-extractor` es una herramienta poderosa diseñada para interactuar
con el Visual Studio Code Marketplace, permitiendo la extracción de
metadatos, análisis de extensiones, y procesamiento de estadísticas
relacionadas con repositorios de GitHub. Ideal para desarrolladores e
investigadores que buscan analizar extensiones populares o
personalizadas.

## Instalación

Puedes instalar la biblioteca de las siguientes maneras:

### Desde GitHub

``` python
pip install git+https://github.com/benjaminserrano23/vscode-extractor.git
```

### Desde PyPI

``` python
pip install vscode-extractor
```

### Desde Conda

``` python
conda install -c benjaminserrano23 vscode-extractor
```

## Características

- Extracción de Metadatos: Recopila información detallada de extensiones
  del Marketplace de Visual Studio Code.

- Análisis de GitHub: Integra datos de los repositorios de GitHub
  asociados, como métricas de código, commits recientes y mucho más.

- Exportación de Datos: Convierte resultados en formatos JSON y CSV para
  facilitar el análisis.

- Procesamiento Escalable: Soporta la extracción de datos para un número
  configurable de extensiones.

## Uso Básico

### Extracción de Extensiones

``` python
from data_collection_benjamin.extension_metadata_extractor import ExtensionMetadataExtractor
from dotenv import load_dotenv
import os

# Cargar las variables de entorno desde el archivo .env
load_dotenv()

if __name__ == "__main__":
    github_token = os.getenv("GITHUB_TOKEN")  # Obtener el token de GitHub desde las variables de entorno
    extractor = ExtensionMetadataExtractor(github_token)
    extractor.run(max_results=10)  # Puedes cambiar a 100 si lo deseas
```

### Exportación a CSV

Los datos extraídos se guardan en JSON y se convierten automáticamente a
CSV:

``` python
data/1_extensions_initial.json
data/1_extensions_initial.csv
```

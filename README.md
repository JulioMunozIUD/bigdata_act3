# bigdata_act3

## Clonar el Repositorio

* https://github.com/JulioMunozIUD/bigdata_act3.git

## Crear y Activar un Entorno Virtual

* python -m venv venv
* source venv/bin/activate  # En Linux/Mac
* venv\Scripts\activate     # En Windows

## Instalar Dependencias

* pip install --upgrade pip
* pip install -e .

## Ejecución del Script de Limpieza

### El script realiza las siguientes acciones:

* Extracción: Se cargan los datos base desde cleaned_data.xlsx.

* Lectura de Datos Adicionales: Se obtiene RickAndMortyScripts.xlsx.

* Enriquecimiento: Se fusionan ambos datasets en la hoja episodes.

* Generación de Evidencia: Se genera enriched_data.xlsx y el reporte de auditoría enriched_report.txt.

* Guarda los datos limpios en cleaned_data.xlsx.

* Genera un informe de auditoría en enriched_report.txt.

## Workflow Automatizado en GitHub Actions

### El proceso de Enriquecimiento de Datos se ejecuta automáticamente en GitHub Actions    cuando hay un push en la rama main. El workflow bigdata.yml sigue los siguientes pasos:

* Clonar el repositorio.

* Configurar Python en la versión 3.9.2.

* Crear y activar un entorno virtual.

* Actualizar pip e instalar las dependencias.

* Ejecutar enrichement.py

* Generar y almacenar los archivos resultantes.

* Realizar un commit automático con los cambios generados.


## Estructura del proyecto

├── setup.py
├── README.md
├── .github
│   └── workflows
│       └── bigdata.yml
└── src
    ├── static
    │   └── auditoria
    │       └── enriched_report.txt
    ├── db
    │   ├── ingestion.db
    │   ├── RickAndMortyScripts.xlsx
    │   └── cleaned_data.xlsx
    ├── xlsx
    │   ├── enriched_data.xlsx
    └── enrichment.py
  
        
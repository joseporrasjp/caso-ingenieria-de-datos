# caso-ingenieria-de-datos
Para esta prueba técnica construí una solución ETL basada en PySpark. La arquitectura utiliza OmegaConf.
Para resolver el este caso las pruebas se realizacron de forma local en Windows, automaticé el paso de escritura utilizando Pandas como puente; esto me permitió omitir el metodo Hadoop y exportar los datos por fecha tanto en formato Parquet como en CSV de forma eficiente.


# Estructura del Repositorio
```
caso-ingenieria-de-datos/
│
├── config/
│   └── config.yaml
│
├── data/
│   ├── input/ ── data_entrega_productos.csv
│   └── processed/
│
├── notebooks/
│   └── ETL_CASO_INGENIERIA_DATOS.ipynb
│
├── requirements.txt
└── README.md
```
# Entorno de Desarrollo y Dependencias
La solución fue desarrollada de forma local y probada exitosamente en el siguiente entorno de un Notebook de Jupyter en Visual Studio Code:

- **pyspark==** 3.5.3
- **pandas**
- **omegaconf**

## Flujo de Trabajo

```mermaid
graph LR
    %% Nodos Principales
    Input[Entrada CSV] --> Filtro(Filtros)
    Filtro --> Transformacion(Transformación y Limpieza)
    Transformacion --> Salida[Generación de Archivo Parquet]

    %% Detalles de Salida
    Salida -.-> Parquet[(Parquet)]
    Salida -.-> CSV[(CSV)]

    %% Estilos simples para que se vea limpio
    style Input fill:#fff,stroke:#333,stroke-width:2px
    style Transformacion fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    style Salida fill:#dcedc8,stroke:#33691e,stroke-width:2px

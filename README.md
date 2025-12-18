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

# Solución desarrollada con las siguientes librerias
- **pyspark==** 3.5.3
- **pandas**
- **omegaconf**
- **pyarrow**

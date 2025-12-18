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
    Bronze[Input: Datos Crudos CSV] --> ETL(Proceso ETL: Limpieza y Reglas)
    ETL --> Silver[Salida: Capa Silver]

    %% Detalles Técnicos de la Salida
    Silver -.-> Formato[Formato: Parquet y CSV]
    Silver -.-> Estrategia[Particionado por fecha]

    %% Estilos Definidos (Letra negra, Negrita, Borde grueso negro)
    style Bronze fill:#f5f5f5,stroke:#000000,stroke-width:3px,color:#000000,font-weight:bold
    style ETL fill:#e1f5fe,stroke:#000000,stroke-width:3px,color:#000000,font-weight:bold
    style Silver fill:#e0f2f1,stroke:#000000,stroke-width:3px,color:#000000,font-weight:bold
    
    %% Estilo para los nodos secundarios (para que también tengan letra negra)
    style Formato fill:#ffffff,stroke:#000000,stroke-width:2px,color:#000000
    style Estrategia fill:#ffffff,stroke:#000000,stroke-width:2px,color:#000000

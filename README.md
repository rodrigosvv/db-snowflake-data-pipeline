# ELT - Sample Data: TPC-H

El objetivo del proyecto es demostrar cómo construir una canalización ELT (Extract, Load, Transform) de forma práctica. Para ello se utilizaron herramientas como DBT (Data Build Tool) para la transformación, Snowflake para el almacenamiento de datos y Airflow para la orquestación. El proyecto pretende cubrir técnicas básicas de modelado de datos, como la creación de fact tables y data marts.


## Schema del Dataset

### Tech Stack
- Python
- Airflow
- Docker
- dbt 
- Snowflake
- SQL
- YAML
- Astronomer Cosmos

### Setup de Snowflake

#### Worksheet



### Configurar dbt_project.yml y packages



#### Creación de fólders staging y marts dentro de carpeta models (Good Practice) 

### Creación de source y staging tables

### Modelos transformados: Fact tables y Data marts

### Creación de Macros

### Generic y Singular Tests


### Deploy usando Airflow y Astronomer Cosmos

#### Modificar Docker file y Requirements file

#### Creación del DAG: dbt_dag.py

#### Creación de Conexión a Snowflake desde Airflow UI

![Snowflake_conn](https://github.com/rodrigosvv/db-snowflake-data-pipeline/assets/143859478/b44de06d-e6fe-4f27-a907-f04fcb65d159)

### ¡Data Pipeline en acción!

![Pipeline success](https://github.com/rodrigosvv/db-snowflake-data-pipeline/assets/143859478/094ab72b-e52c-4352-9cb4-2c1d2109e466)



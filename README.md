# ELT - Sample Data: TPC-H

El objetivo del proyecto es demostrar cómo construir una canalización ELT (Extract, Load, Transform) de forma práctica. Para ello se utilizaron herramientas como DBT (Data Build Tool) para la transformación, Snowflake para el almacenamiento de datos y Airflow para la orquestación. El proyecto pretende cubrir técnicas básicas de modelado de datos, como la creación de fact tables y data marts.


## Schema del Dataset

<img width="615" alt="sample-data-tpch-schema" src="https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/3f597068-4094-433c-a519-fb5612c348b5">

Fuente: [docs.snowflake.com/en/user-guide/sample-data-tpch](https://docs.snowflake.com/en/user-guide/sample-data-tpch)

## Tech Stack
- Python
- Airflow
- Docker
- dbt 
- Snowflake
- SQL
- YAML
- Astronomer Cosmos

## Setup de Snowflake

#### Worksheet

![snowflake setup](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/81609ebc-ec0b-4db7-9193-5968bac3bce3)

### Configurar dbt_project.yml y packages

#### dbt_project.yml
![models_configuration](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/47577fbb-dec2-4b46-96d0-5e07bb1eb82a)

#### Packages
![packages](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/d05db765-e31f-43bb-a927-85042f7bcc62)

#### Creación de fólders staging y marts dentro de carpeta models (Good Practice) 

![folders](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/1d96211a-fb0f-46d9-a6e8-d840e7d9e910)

## Creación de source y staging tables

#### Source 
![sourcers](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/31b64687-ee38-4906-bbb5-c5ec59300419)

#### Staging Tables
![stg_orders](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/727b3ff3-9976-4e68-b05c-ec84db06168e)
![stg_lineitems](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/12652ed7-1d36-40c2-9d26-b371cf2af71e)

## Modelos transformados: Fact tables y Data marts

#### Fact Table
![facttable](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/2477af40-19c8-44cd-8d04-0fe88f0187d4)

#### Data marts
![int_order_items](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/23c1b3cf-256f-4fbd-8784-ba7b5cc3d9b3)
![mart_order_items](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/46df313e-8630-4290-ac5f-7307329ab306)

### Creación de Macros

![Macro](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/d087dd02-e64b-469f-964a-27e53f88ea20)

## Generic y Singular Tests

#### Generic Test

![generic_Test](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/067e409d-ffbf-4a31-8026-db1d3fffc06d)

#### Singular Tests

![singulartest_1](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/b29356a6-3d9a-4c48-b5c3-f12caa54d311)

![singultartest_2](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/c68a7eed-8991-4856-8766-1643b3daf492)

## Deploy usando Airflow y Astronomer Cosmos

### Modificar Docker file y Requirements file

#### Docker File
![Docker environment](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/7455a833-ee0c-404e-b3ae-13c7c46704b7)

#### Requirements File
![requerimientos](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/c68b2da7-d167-49d9-871f-dc9fe58569c8)

#### Creación del DAG: dbt_dag.py

![dag_id](https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/1fded84c-186b-4dcd-b918-454e05e2c19e)

#### Creación de Conexión a Snowflake desde Airflow UI

![Snowflake_conn](https://github.com/rodrigosvv/db-snowflake-data-pipeline/assets/143859478/b44de06d-e6fe-4f27-a907-f04fcb65d159)

## ¡Data Pipeline en acción!

![Pipeline success](https://github.com/rodrigosvv/db-snowflake-data-pipeline/assets/143859478/094ab72b-e52c-4352-9cb4-2c1d2109e466)



# ELT - Sample Data: TPC-H

El objetivo del proyecto es demostrar cómo construir una canalización ELT (Extract, Load, Transform) de forma práctica. Para ello se utilizaron herramientas como DBT (Data Build Tool) para la transformación, Snowflake para el almacenamiento de datos y Airflow para la orquestación. El proyecto pretende cubrir técnicas básicas de modelado de datos, como la creación de fact tables y data marts.


## Schema del Dataset

<img width="615" alt="sample-data-tpch-schema" src="https://github.com/rodrigosvv/db-snowflake-elt-pipeline/assets/143859478/3f597068-4094-433c-a519-fb5612c348b5">

Fuente: [docs.snowflake.com/en/user-guide/sample-data-tpch](https://docs.snowflake.com/en/user-guide/sample-data-tpch)

## Tech Stack
- <img alt="Python" src="https://img.shields.io/badge/Python-_?logo=python&color=white" />
- <img alt="Apache Airflow" src="https://img.shields.io/badge/Apache_Airflow-_?logo=apacheairflow&color=red" />
- <img alt="Docker" src="https://img.shields.io/badge/Docker-_?logo=docker&color=lightblue" />
- <img alt="dbt" src="https://img.shields.io/badge/dbt-_?logo=dbt&logoColor=%23FF694B&color=gray" />
- <img alt="Snowflake" src="https://img.shields.io/badge/Snowflake-_?logo=snowflake&logoColor=white&color=%2329B5E8" />
- <img alt="YAML" src="https://img.shields.io/badge/YAML-_?logo=yaml&logoColor=white&color=%23CB171E" />
- <img alt="Astronomer Cosmos" src="https://img.shields.io/badge/Astronomer%20Cosmos-_?logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyBoZWlnaHQ9IjMwMCIgdmlld0JveD0iMCAwIDMwMCAzMDAiIHdpZHRoPSIzMDAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiPjxsaW5lYXJHcmFkaWVudCBpZD0iYSIgeDE9IjIwLjAwNzI2NCUiIHgyPSI4Mi4xOTA0MTclIiB5MT0iLTUuNTMwODkxJSIgeTI9Ijg5LjMwMzM5NSUiPjxzdG9wIG9mZnNldD0iMCIgc3RvcC1jb2xvcj0iIzk0NzhkMiIvPjxzdG9wIG9mZnNldD0iMSIgc3RvcC1jb2xvcj0iIzU5NDE4ZCIvPjwvbGluZWFyR3JhZGllbnQ%2BPHBhdGggZD0ibTE0Ni4wODY2NDcuMDgxNTQ2MzZjLTQwLjMyNTE3OSAxLjMwNTc0ODUyLTc3LjcyNTc2MjggMTguMjM0MTY4OTQtMTA1LjMxNjYyMTYgNDcuNjcwMzkxNjQtNTYuOTU1NjAyNSA2MC43NjYxMzMtNTMuODU0ODI3MyAxNTYuNTM5ODE3IDYuOTA5MjkyMyAyMTMuNDk2NDI2IDIxLjMxMzgwMjUgMTkuOTc1ODM4IDQ2Ljk0MzUyMTYgMzIuNTMzOTc4IDczLjY4NjcwMTMgMzcuODM3NTExbDguMDE1NzA1LTIwLjA0MjI4M2MtMjQuMzg1MzgyLTQuMDc0Mjk4LTQ3Ljg2ODcyMDYtMTUuMTA5MjMyLTY3LjIyMDM3NjctMzMuMjQ2NzUzLTUyLjI0MzAyODI5LTQ4Ljk3MTEwNy01NC45MDg4ODk1Ni0xMzEuMzE0ODA5LTUuOTM5Nzk2Ni0xODMuNTU5ODUxMiAyMy43MjI5NDM3LTI1LjMwODU2NzQgNTUuODgwMzk4My0zOS44NjcxMDk2IDkwLjU1MDY4OTMtNDAuOTg4NjIzOCAxLjQzNzYzMi0uMDQ3MzE3IDIuODc0MjU4LS4wNjg0NTg2IDQuMzA3ODYzLS4wNjg0NTg2IDI2LjE1MDIwNiAwIDUxLjIwMDA0IDcuNzU2OTcxNyA3Mi41MzQ5ODQgMjIuMjIxODg2Nmw4LjAyNzc4Ny0yMC4wNzQ0OTkxYy0yMy45NjU1Ny0xNS4yMDY4ODYxNy01MS42ODYyOTktMjMuMzI3MjkyOS04MC41NDg2NzctMjMuMzI3MjkyOS0xLjY2NjE2MyAwLTMuMzM0MzQuMDI3MTgyMTItNS4wMDc1NS4wODE1NDYzNnptMTUuMjg4NDMyIDc2LjYzNzQ3MTA0aC0yMC4zMzcyNTktLjY4MTU2N2wtLjI1MzcuNjMzMjQyNy01My41MTQ1NDcxIDEzMy43ODUzNjE5LS41NTE2OTY0IDEuMzgxMjU0aDEuNDg2OTYyNyAyMS41OTc3MDQ4LjY4ODYxNGwuMjQ4NjY2LS42NDIzMDMgMTMuMTI5OTctMzMuNzYwMTkzaDU3LjcwNTYyOGwxMy4yOTUwNzcgMzMuNzY1MjI3LjI1MDY4LjYzNzI2OWguNjg2NiAyMi4zNjA4MTcgMS40ODY5NjNsLS41NTI3MDMtMS4zODEyNTQtMzQuNTU0NTE1LTg2LjM4Njc5MS0uMjUyNjkzLS42MzIyMzZoLS42ODI1NzQtMjEuNjE5ODUzLTEuNDcxODYxbC41MzM1NzUgMS4zNzExODcgMTIuMjU2MTE2IDMxLjUwMTA1N2gtNDEuMDEyNzg2bDMwLjY5NzY3NS03OC44OTk2Mjc5LjUzMzU3NS0xLjM3MjE5Mzd6IiBmaWxsPSJ1cmwoI2EpIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE3LjI1KSIvPjwvc3ZnPg%3D%3D&color=%23D6D6D6
" />


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



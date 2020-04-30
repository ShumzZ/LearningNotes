source: https://retina.ai/blog/dataops-at-retina/

An Inside Look at DataOps at Retina
By BRAD ITO, CTO & CO-FOUNDER

- Data needs at retina
  - apply ML to make predictions based on clients' customer data
  - team use R and Python to interact with data programmatically
  - data comes in in diverse forms (technology and schema) and sizes
  - process time is ambitious
- Build a data platform
  - cloud native; separate storage and computation
    - data stored in AWS s3/ Azure Blob Storage
      - easier access and enforcement of security and data retention policies
    - compute uses Apache Spark
      - fast: in-memory based distributed computation and columnar data storage
      - large ecosystem of data connectors to help with data ingest and process
    - use Databricks multi-language notebook environments to create data pipeline, perform data validation/cleaning and data exploration/modeling
      - **common libraries** used to reduce code repetition and provide fast implementation of new models or datasets
      - **production notebooks** version controlled, tested, and kept clean and in reliable working order
      - **ad-hoc and research notebooks** used for exploration and new model development
    - a typical workflow: start a new model in an ad-hoc notebook and possibly a few variants --> when the new model is well understood, the notebook is converted into production notebook where inputs are parameterized, edge cases are properly handled, testability is improved --> if the common function are needed across multiple notebooks, they are then built into a common custom package that includes automated tests and stricter version control.
- Create reproducible environments

  data science team nowadays could leverage multiple external packages but the associated cost is to manage the dependency issues, since the newer version might break backward compatibility of simply contain bugs.
  - Use Conda to capture the Python runtime and exact versions of its libraries. Ad-hoc notebook may contain newer versions but they will update the common notebook/environment when productized.
  - Use Docker to capture and replicate compiled C code behind many Python libraries, as well as runtime dependencies (esp. those maintained by an operating system)

- Allow for different data formats
  - Apache Parquet
    - supports Python & R
    - native to Apache Spark, allow read and write in a distributed maner
    - permits to define and enforce data type for each column
    - uses columnar storage, particularly efficient for the sparse data in ML
    - drawback: dose not support streaming data well; not designed for indices that used in database for fast selection of single rows of data

- Ensure data connectivity
  - [Databricks Connect](https://docs.databricks.com/dev-tools/databricks-connect.html) allows connection to Databricks/Spark clusters through common IDE's (PyCharm, RStudio), notebook servers(Zeppelin, Jupyter) and access to AWS access

- Protect data reproducibility
  - different stages of data pipelines process data in an idempotent way and treat data as immutable (enforced by generating new paths each time data is output). This incurs data duplication but idempotency ensures that re-run a certain data pipeline on the same data input will not lead to data corruption
  - idempotent and mutable data store also exist and are enforced by generating sub-paths using name Hive partitions and ensuring each run writes to a separate partition. Then when read in, by convention hive will treat the sub-paths as another column in the dataset.

- Automating quality checks
  - data comes in from client and external systems as 'raw' data and get transformed only to the extend that they can be converted into parquet format.
  - data is then validated and turns into data lake where multiple teams can access the data (also known as democratized)in a clean form

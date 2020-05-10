source: https://towardsdatascience.com/a-data-engineers-perspective-on-data-democratization-a8aed10f4253

- data democratization: make data accessible by removing barriers and bottlenecks between data and teams who leverage data to make decisions, or produce reports/ products/ services

- motivation: pre-cloud/any forms or distributed system, centralized data storage/ processing is maintained by a data team and this team soon become the bottleneck:
  - other teams have only access to highly processed data(reports, tables, dashboards) and thus domain experts may not explore data as needed
  - data consumers have little knowledge and the processing procedure of the data, lack of transparency lead to poor understanding and confidence in the data
  - domain experts need to throughly define the requests since they do not participate in modeling and transformation, might be time wasted

- How democratized?
  - data accessibility should be unequal based on a person/ team 's technical ability, the degree of democratization is gauged in following aspects, i.e. how easy to:
   - discover available datasets
   - browse metadata(tables, columns, update frequency, update strategy, health of table/ QC metrics, etc.)
   - explore raw/ unprocessed data
   - create & share insights, findings
   - generate new dataset from existing ones
   - ingest new data source

- how to democratize data
  - team structure
    - embed data engineers in each team, allowing teams to be relative independent data-wise; data engineers could work more closely with domain experts
    - data platform team: provide infrastructure and tooling to help reduce technical difficulties to perform common tasks: provide web service for anyone to ingest arbitrary files into data lake; host Airflow and provide it as a service to other data teams; abstract away the configuration and maintenance of Spark clusters and provide analytics/ ML team with EMR templates
  - metadata hub
    - often takes the form of an internal search engine or set of documentations to catalogue metadata of all the datasets: table contents, table owner, health of datasets(QC scores), data lineage (Airflow DAG), update strategy etc.
    - [a dedicated blog](https://towardsdatascience.com/how-linkedin-uber-lyft-airbnb-and-netflix-are-solving-data-management-and-discovery-for-machine-9b79ee9184bb) on various metadata hubs: AirBnb’s Dataportal, Uber’s Databook, Netflix’s Metacat, Lyft’s Amundsen, and most recently Google’s Data Catalog, and LinkedIn’s DataHub
  - data quality checks (QC)
    while data creation is distributed, the quality checks also need to be distributed, further check out open source project [great expectation](https://medium.com/@expectgreatdata/down-with-pipeline-debt-introducing-great-expectations-862ddc46782a)
  - data engineering role
    - DE shouldn't write data pipelines they do not use, a dedicated blog on DE roles and [refection on Data Science Team building](https://multithreaded.stitchfix.com/blog/2016/03/16/engineers-shouldnt-write-etl/); DE should help simplify writing data ETL and company should train data consumers to do the job themselves.
    - instead of crafting individual data pipeline, DE should focus more on providing tools to help creating/ maintaining data pipelines as a whole.
    DE should focus on keeping data accessible by data consumers with minimal or no intervention from engineering.

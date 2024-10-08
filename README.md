# Observe introduction
Observe collects all of your data, system and application logs, metrics, tracing spans, and any other kind of data then ingests them into a data lake. Then, depending on your individual use case, Observe curates the relevant event data into datasets. Datasets can be linked to other datasets to make it easy for you to access and correlate relevant context during an event investigation. You can then package up datasets, along with dashboards and alerting conditions(monitors), to produce Observe applications.

## Datastreams
Observe ingests event data using datastreams. Once ingested, all event data associated with a specific datastream populates a dataset. A datastream ingests data from multiple different sources with each source identified by a unique token. Individual tokens may be enabled, disabled, or deleted without impacting data associated with a different token on the same Datastream. This allows you to easily rotate datastream tokens.

## Datasets
Datasets are much like tables in a database. They consist of rows and columns of specific types. They can be linked, joined, and aggregated to derive insights. But unlike traditional tables, datasets automatically grow as Observe collects new data. Datasets are much like tables in a database. They consist of rows and columns of specific types. They can be linked, joined, and aggregated to derive insights. But unlike traditional tables, datasets automatically grow as Observe collects new data.

# Goal: Building an Observe intance with SIEM capabilities

## Requirements
- Setup free Observe trial: https://account.observeinc.com/


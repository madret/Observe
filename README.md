# Observe introduction
Observe collects all of your data, system and application logs, metrics, tracing spans, and any other kind of data then ingests them into a data lake. Then, depending on your individual use case, Observe curates the relevant event data into datasets. Datasets can be linked to other datasets to make it easy for you to access and correlate relevant context during an event investigation. You can then package up datasets, along with dashboards and alerting conditions(monitors), to produce Observe applications.

## Datastreams
Observe ingests event data using datastreams. Once ingested, all event data associated with a specific datastream populates a dataset. A datastream ingests data from multiple different sources with each source identified by a unique token. Individual tokens may be enabled, disabled, or deleted without impacting data associated with a different token on the same Datastream. This allows you to easily rotate datastream tokens.

## Datasets
Datasets are much like tables in a database. They consist of rows and columns of specific types. They can be linked, joined, and aggregated to derive insights. But unlike traditional tables, datasets automatically grow as Observe collects new data. Datasets are much like tables in a database. They consist of rows and columns of specific types. They can be linked, joined, and aggregated to derive insights. But unlike traditional tables, datasets automatically grow as Observe collects new data.

# Goal: Building an Observe intance with SIEM capabilities

## Requirements
- Setup free Observe trial: https://account.observeinc.com/

## 1. Host quickstart
The Host Quick Start Integration is the simplest way to start monitoring your Linux and Windows endpoints in Observe. It is designed to quickly surface logs and metrics information in our Log and Metric explorers.
The package uses the Observe Agent for Linux and Windows, and OpenTelemetry Collector with the Open Telemetry Host Metrics Receiver and the Open Telemetry File Log Receiver for MacOS to ship common logs and metrics from the host you wish to monitor.
The install is designed to be simple and light weight to simplify the process.
The instructions are located in a public git hub repository and are also provided (with pre-populated parameters to make it work for your Observe instance) within the Configuration panel of our UI based install for the app. 

Observe helps you quickly start monitoring the health and activity of your servers with the following features:
- A logs dataset (Logs) with log files being shipped from your host.
- A metrics dataset (Metrics) with common host metrics collected from your host.
- A resource dataset (Source) to quickly show you the hosts your are monitoring that links to associated logs and metrics.
- A simple home dashboard that shows high level logs and metrics with links to our log, metric and resource explorers.
- A simple health dashboard to monitor the health of the otelcol agent installed on your server.

## 2. Install observe agent
Scope: Windows OS

### WINOS Install
Install the observe-agent package via the provided installation powershell script. This script needs to be run in a powershell terminal that you run as administrator. Replace `OBSERVE_TOKEN` and `OBSERVE_COLLECTION_ENDPOINT` with the appropriate values and run on each host.

`[Net.ServicePointManager]::SecurityProtocol = "Tls, Tls11, Tls12, Ssl3"; Invoke-WebRequest -UseBasicParsing "https://raw.githubusercontent.com/observeinc/observe-agent/main/scripts/install.ps1" -outfile .\install.ps1; .\install.ps1 -observe_token "${OBSERVE_TOKEN?}" -observe_collection_endpoint "${OBSERVE_COLLECTION_ENDPOINT?}"`

#### Check Status
`Get-Service ObserveAgent
Set-Location "${Env:Programfiles}\Observe\observe-agent"
PS C:\Program Files\Observe\observe-agent> ./observe-agent status`
#### Uninstall:
`Stop-Service ObserveAgent
Remove-Item -Recurse "${Env:Programfiles}\Observe"`


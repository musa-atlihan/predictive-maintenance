# predictive-maintenance
Time to failure (TTF) using Weibull distribution and recurrent neural networks in Keras.

## How to get the dataset?
I am using a dataset from Microsoft that is composed of 5 csv files (a dataset collected by [Fidan Boylu Uz](https://azure.microsoft.com/en-au/blog/author/fboylu/) from Microsoft). 

- `mkdir -p ml/data/dataset`
- `cd ml/data/dataset`

```bash
wget https://azuremlsampleexperiments.blob.core.windows.net/datasets/PdM_telemetry.csv
wget https://azuremlsampleexperiments.blob.core.windows.net/datasets/PdM_errors.csv
wget https://azuremlsampleexperiments.blob.core.windows.net/datasets/PdM_maint.csv
wget https://azuremlsampleexperiments.blob.core.windows.net/datasets/PdM_failures.csv
wget https://azuremlsampleexperiments.blob.core.windows.net/datasets/PdM_machines.csv
```

Please download all 5 csv files into `ml/data/dataset` folder.

## Dataset components and features
**telemetry.csv** The first data source is the telemetry time-series data which consists of voltage, rotation, pressure and vibration measurements collected from 100 machines in real time averaged over every hour collected.

**errors.csv** The errors logs are non-breaking errors thrown while the machine is still operational and do not constitute as failures. The error date and times are rounded to the closest hour since the telemetry data is collected at an hourly rate.

**maint.csv** This file contains the scheduled and unscheduled maintenance records which correspond to both regular inspection of components as well as failures. A record is generated if a component is replaced during the scheduled inspection or replaced due to a break down. The records that are created due to break downs will be called failures which is explained in the later sections.

**machines.csv** This data set includes some information about the machines which are model type and years in service.

**failures.csv** These are the records of component replacements due to failures. Each record has a date and time, machine ID and failed component type.

## Create Anaconda environment and install requirements
- `cd ml`
- `conda create --name predictive-maintenance python=3.6`
- `source activate predictive-maintenance`
- `pip install -r requirements.txt`
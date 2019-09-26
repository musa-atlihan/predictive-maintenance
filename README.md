# predictive-maintenance
Time to failure (TTF) using Weibull distribution and recurrent neural networks in Keras.

## How to get the dataset?
I am using a dataset from Microsoft that is composed of 5 csv files (a dataset collected by [Fidan Boylu Uz](https://azure.microsoft.com/en-au/blog/author/fboylu/) from Microsoft). 
Please go to this [link](https://gallery.azure.ai/Experiment/Predictive-Maintenance-Implementation-Guide-Data-Sets-1) and follow to instructions to download the files.
On the page, click the `Open in Studio` button and then:

`
Open the experiment in Studio and run the experiment. Once the experiment has successfully run, right click the output ports of Convert to csv modules, and use Save as Dataset option to save the datasets to your workspace. Use the exact names provided in the Import Data module descriptions which are telemetry, errors, maint, machines and failures to name these datasets as you save them.
`

Please download all 5 csv files into `ml/data/ms-dataset` folder.

## Create Anaconda environment and install requirements
- `cd ml`
- `conda create --name predictive-maintenance python=3.6`
- `source activate predictive-maintenance`
- `pip install -r requirements.txt`
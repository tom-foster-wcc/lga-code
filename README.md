# Overview

This work was presented as part of a two part Introduction to Data Science in local government. For the Local Government Association's Advanced and Predictive Analytics Network (APAN).

If you are looking to recreate the work yourself, the local_lga_demo.ipynb is the file of interest, but don't forget you need to download one of the files yourself! [See Data Sources for more](#sources)

## Contents

* [Installation](#installation)
    * [Python Environment - Default set up](#python-environment-on-the-windows-linux-subsystem-wsl2)
    * [Alternative using VS Code](#alternatively-vs-code)
    * [Out of scope tools](#whats-out-of-scope)
* [Data Sources](#sources)




# Installation

## Python Environment on the Windows Linux Subsystem (WSL2)

You will need to have a version of Python 3.8.10 or later working to make use of this work. (However it is likely that the code itself can be used for older versions - but this isn't tested).

To recreate the virtual environment after pulling the files. Change into the directory and activate the environment.

This assumes you are working with Ubuntu WSL2 but should work on Windows. (It should work on a Linux install too).

If it's in Windows environment take notice of the comments within the code sections.

```bash
# Change into the directory
cd lga-code
# Create the virtual environment
python3 -m venv venv
# Active the virtual environment 
# venv/Scripts/activate if it's on windows
source venv/bin/activate
```

Once activated recreate the environment from the requirements.txt file.

```bash
# This will go line by line to avoid complete failures
# you may have some failures though. You can ignore
# them for now.
cat requirements.txt | xargs -n 1 pip install
```

To then start the Jupyter Lab / Jupyter notebook you need to then run a command to launch a web service.

```bash
jupyter lab
```

This will then launch a local web server. From the command output you want to copy the URL which starts contains localhost.

```bash
# Output should look like this
Or copy and paste one of these URLs:
        http://localhost:8888/?token=380d34f0.....8a
```

## Alternatively, VS Code

You can use Visual Studio Code and work solely in Visual Studio which will pick up your environment and set up a virtual environment.

If you're familiar with Visual Studio Code - it's assumed you will know how to set up the environment.
___

## What's out of scope

Unfortunately, it's out of scope to consider the wide amount of tools available.

It is useful to look at tools such as:

* git
* vs code
* wsl2
* postgis / postgresql
* sql as a language

If you're focus is more in health or public health you should consider looking at:

* R as a language (it's more common in the field - but has it's drawback with production)


___

# Sources

We are using data sources from the ONS, as well as from our own internal system geospatial system.

One of the files is too large to upload to Github and can be found at the following link:

* [Population estimates for Lower layer super output areas (LSOA) in England and Wales, single year of age and sex, mid-2001 to mid-2017](https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates/adhocs/009983populationestimatesforlowerlayersuperoutputareaslsoainenglandandwalessingleyearofageandsexmid2001tomid2017)

The other sources in the data folder exist as part of the project however, for population estimates you can find them at:
* [Lower layer Super Output Area population estimates (supporting information - we used 2018 and 2019)](https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates/datasets/lowersuperoutputareamidyearpopulationestimates)

From our own internal system we have used and joined tables related to local names. For the purposes of reproducibility. This has been stored in the data folder as `local_names.csv`.




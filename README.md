# Talkspace Data Exploration and Analysis
This project contains two identical analyses done with R and Python in Jupyter notebooks exploring my own scraped Talkspace data. Any Talksapce user can plug in their own data, draw their own conclusions, and expand on their own questions using this existing framework.

## Setting up your environmnet
This project manages both its [R](https://github.com/vaughn-johnson/talkspace-notebook/blob/main/r_env.yml) and [Python](https://github.com/vaughn-johnson/talkspace-notebook/blob/main/python_env.yml) environmnets using [conda](https://docs.conda.io/en/latest/). To quote from the [conda documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html):


> ### Creating an environment from an environment.yml file
> Use the terminal or an Anaconda Prompt for the following steps:
>
> 1. Create the environment from the environment.yml file:
>   - `conda env create -f [either r_env or python_env].yml`
>   - The first line of the yml file sets the new environment's name. For details see Creating an environment file manually.
>
> 2. Activate the new environment using `conda activate myenv`
>
> 3. Verify that the new environment was installed correctly:
>   - `conda env list`
>   - You can also use `conda info --envs`

## Using your own Talkspace Data
You can scrape your own data and point the notebook to it.
Ideally, this process would be a little smoother for you, but given the sensitive nature of this data, 
I would rather add some hurdles to make sure people are properly vetting who they are giving their
Talkspace credentials to.

[![asciicast](https://asciinema.org/a/gZxSWHvP7QWDLHdUgnT6E5v1N.svg)](https://asciinema.org/a/gZxSWHvP7QWDLHdUgnT6E5v1N)

1. Clone this repository to your local machine.
2. Follow the instructions [here](https://github.com/vaughn-johnson/talkspace-scraper) to scrape your own data into a MongoDB server. You can set up a server in the cloud for free [here](https://www.mongodb.com/cloud/atlas) or you can install MongoDB locally [here](https://docs.mongodb.com/manual/installation/)
3. From Step 1, you should procure a [MongoDB connection string](https://docs.mongodb.com/manual/reference/connection-string/). Copy this string to your clipboard and navigate to the directory you cloned this respository to. When you are in the `talkspace-notebook` directory, run the following command to set the environment to point to your own
```
echo -e "MONGO_CONNECTION_STRING=$(pbpaste | cat)" > .env
```
4. Verify your environment is set correctly by running `cat .env` and seeing somethign resembling
```
mongodb://mongodb0.example.com:27017
```
5. You're all set! You can use both notebooks the way you normally would be running cells.

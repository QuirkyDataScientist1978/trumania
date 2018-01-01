# data-generator

## Documentation and tutorial

See https://realimpactanalytics.atlassian.net/wiki/display/LM/Data+generator+tutorial

You can also have a look at the S&D example Scenario here in `tests/scenarios/snd`

## How to install 

The data-generator is not (yet) packaged in any special way, the way it is used at the moment is simply to have the code, the required dependencies, and execute the necessary python script directly. 

Make sure you have python 2.7 and pip installed.

Then, if pipenv is not yet present on your laptop, install it: 

```sh
pip install --user pipenv
```

Otherwise, make sure you have the latest version:

```sh
pipenv --update
```

then install all dependencies for this project: 
```sh
pipenv install
```

See [https://docs.pipenv.org](https://docs.pipenv.org) for more details about how to use pipenv to handle python dependencies.


## Run unit tests locally

Enter the virtual env of the project: 

```sh 
pipenv shell
```

Then execute the unit tests: 
```sh
py.test -s 
```

## Test data
Some folders are stored on S3:

`datagenerator/components/_DB` is on `s3://lab-data-generator-db`

`datagenerator/components/geographies/source_data` is on `s3://lab-data-generator-geographies`

You can download them with aws-cli:

```sh
pip install awscli
mkdir datagenerator/components/_DB
cd datagenerator/components/_DB
# make sure you have your AWS env variables set
aws s3 cp s3://lab-data-generator-db . --recursive
```


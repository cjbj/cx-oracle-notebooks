# Python cx_Oracle Notebooks, 2022

The repository contains Jupyter notebooks showing best practices for using cx_Oracle, the Python DB API for Oracle Database.

## Setup

An existing Oracle Database is required.

The JSON demo assumes Oracle Database and Oracle Client are 21c.

### Install Python 3

Install Jupyter (see https://jupyter.org/install):

    pip install notebook

### Install cx_Oracle (see https://cx-oracle.readthedocs.io/en/latest/user_guide/installation.html)

    pip install cx_Oracle

### Install some libraries used by the examples:

    pip install numpy matplotlib

### To setup the cx_Oracle sample tables On macOS set up libclntsh by finding the library directory

    python
    import cx_Oracle
    cx_Oracle
    exit()

With the appropriate path from above, create a sym link:

    ln -s $HOME/Downloads/instantclient_19_8/libclntsh.dylib $HOME/.local/lib/python3.9/site-packages/

### Create the cx_Oracle sample schema

Clone/download https://github.com/oracle/python-cx_Oracle/tree/master/samples

    git clone https://github.com/oracle/python-cx_Oracle.git
    rm -rf python-cx_Oracle/doc python-cx_Oracle/odpi python-cx_Oracle/src python-cx_Oracle/test python-cx_Oracle/*.* python-cx_Oracle/.git*

    cd python-cx_Oracle/samples

Review python-cx_Oracle/samples/README.md

Edit python-cx_Oracle/samples/sample_env.py and set desired credentials and connection string

    export CX_ORACLE_SAMPLES_MAIN_USER=pythondemo
    export CX_ORACLE_SAMPLES_MAIN_PASSWORD=welcome
    export CX_ORACLE_SAMPLES_EDITION_USER=pythoneditions
    export CX_ORACLE_SAMPLES_EDITION_PASSWORD=welcome
    export CX_ORACLE_SAMPLES_EDITION_NAME=python_e1
    export CX_ORACLE_SAMPLES_CONNECT_STRING=localhost/orclpdb1
    export CX_ORACLE_SAMPLES_DRCP_CONNECT_STRING=localhost/orclpdb1:pooled
    export CX_ORACLE_SAMPLES_ADMIN_USER=system
    export CX_ORACLE_SAMPLES_ADMIN_PASSWORD=oracle

Install the schema

    python setup_samples.py

### Edit the cloud example credentials and connection string in the first notebook

### Set this environment variable before starting Jupyter:

    export CLOUD_PASSWORD="whatever"

### Start Jupyter:

    cd ../..
    jupyter notebook

Load each notebook *.ipynb file and step through it

Before running the notebooks cells, edit the connect string(s) near the top of each notebook.

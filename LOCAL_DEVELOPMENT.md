# Local Development Setup

## Virtualenv

    vf new -p python3.9 pythondotorg
    cd pythondotorg
    vf connect

## Dependencies

Install development dependencies:

    python -m pip install -r dev-requirements.txt

## MacOS

The tests need a working `pdflatex` command. You can install it with `brew`:

    brew install mactex

## Database

Create the postgres database:

    initdb databases/postgres

Start the postgres server:
    
    postgres -D databases/postgres

Create the database and user:

    createdb pythondotorg -E utf-8 -l en_US.UTF-8 -T template0

After that, you can apply the migrations:

    python manage.py migrate

## Django Setup

    python manage.py migrate
    python manage.py create_initial_data


## Running the Tests

    python manage.py test
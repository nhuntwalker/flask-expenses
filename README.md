# Flask Expense Tracker

A simple Flask web application for listing and tracking expenses.

**Author:** Nicholas Hunt-Walker

## Routes

- `/` - the home page listing all existing expenses
- `/expense/{id:\d+}` - the page for an individual expense
- `/expense/{id:\d+}/edit` - for editing existing expenses
- `/expense/{id:\d+}/delete` - delete an existing expense
- `/expense/{category:\w+}` - list all expenses by category

## Getting Started

- Clone this repository to your machine
- Once downloaded, `cd` into the `flask-expenses` directory
- Within the directory, create a new Python 3.6+ virtual environment (e.g. `python3.6 -m venv env`)
- Activate that virtual environment (`source env/bin/activate`). Note, you'll need to have [sqlite](https://www.sqlite.org/index.html) installed on your machine to run it in development.
- `pip install -r requirements.txt` to install the necessary packages into your virtual environment

## In Development

- Run `python database.py` to set up your sqlite or postgres database. The database will be filled with mock data
- Serve the application on port `5000` with `python application.py`

## In Production

- Set the `DATABASE_URL` environment variable to point to the full database URL to a postgres database. E.g. `postgres://<username>:<password>@<database host>:<port>/<database name>`
- Run `python database.py` to set up the postgres database. Make sure to comment out the lines where the database fills with fake data
- Point a WSGI http server at `application.py` and serve
# Setup Tutorials

Sample instructions for setting up dependencies and installs.

## Software Stack

| Purpose | Technology |
| --- | --- |
| Development Language | Text |
| Web Framework | Text |
| Testing Framework | Text |
| Continuous Integration (Testing) | Text |
| Database | Text |
| Deployment | Text |

## Setup Instructions

### Codebase

Clone the repository and navigate into the directory:
```shell
git clone https://URL.git
cd REPO/
```

### Android

Install [Android Studio](https://developer.android.com/studio/) and import the project.

#### Google Maps API Key (for development builds)

Generate a [Google Maps SDK API key (step 1)](https://developers.google.com/maps/documentation/android-sdk/get-api-key).

In the file `app/src/debug/res/values/google_maps_api.xml`, replace the value of the placeholder key with your API key.

Build and run the Android application on a physical or virtual device.

#### Creating a Production Release

Create a new file in the root directory to hold the secure keystore details:
```shell
cp keystore.properties.template keystore.properties
```

This file will be ignored by Git.

Set your keystore information in this file.

### Heroku

Install the Heroku command line interface by following [these instructions](https://devcenter.heroku.com/articles/heroku-command-line).

Login to Heroku:
```shell
heroku login
```

Create a Heroku application with your preferred app name:
```shell
heroku apps:create APPNAME
```

### Angular

Install [Node.js](https://nodejs.org/en/download/) (which comes with NPM).

Install the required NPM dependencies:
```shell
npm install
```

Install the Angular command-line interface:
```shell
npm install -g @angular/cli
```

To start up the website locally, run:
```shell
ng serve
```

The app will automatically reload if you change any of the source files.

#### Deployment

To build the website generically for deployment, run:
```shell
ng build
```

### Golang

Install [Golang](https://golang.org/doc/install).

Setup the dependencies:
```shell
go get -t ./...
```

Build the server:
```shell
go build
```

Run the executable:
```shell
,/EXEC
```

### Node.js

Install [Node.js](https://nodejs.org/en/download/) (which comes with NPM).

Install the necessary NPM packages:
```shell
npm install
```

Start the server locally:
```shell
npm start
```

#### Google Sheets

Follow [these instructions](https://developers.google.com/sheets/api/quickstart/nodejs) to create a new Google Cloud Platform project and enable the Google Sheets API.

Download the Client JSON file and rename it to `credentials.json`. Place it in this directory (it will be ignored by Git).

Start the server locally:
```shell
npm start
```

Google will guide you through a process to authenticate the server. This will only occur the first time.

#### Deployment (Heroku)

After creating the Google Cloud Platform project in _Setup_ above, create a new set of credentials for the Service Account. Download the secret file and keep it safe.

Create a Heroku application with whichever method you prefer. In your deployment environment, set the following environment variables using values from the secret file:

Environment Variable | Value from Service Account Credentials
--- | ---
`GOOGLE_CLIENT_EMAIL` | `client_email`
`GOOGLE_PRIVATE_KEY` | `private_key`

Ensure that the client email has access to the Sheet; share access to it manually if necessary.

### pdfTeX

_Required packages:_ `texlive texlive-bibtex-extra texlive-publishers`

Install the required packages:
```shell
sudo apt-get install texlive
```

To build the output PDF, run pdfTeX twice:
```shell
pdflatex $FILENAME
pdflatex $FILENAME
```

#### pdfTeX With a Bibliography

Install the required packages:
```shell
sudo apt-get install texlive-bibtex-extra texlive-publishers
```

Build the bibliography (the `.bib` file):
```shell
bibtex $FILENAME
```

Then build the output PDF again, twice:
```shell
pdflatex $FILENAME
pdflatex $FILENAME
```

### Python

If Python 3 is not yet installed, then install the relevant packages:
```shell
sudo apt-get install python3 python3-pip
```

Install the PIP dependencies:
```shell
pip3 install PACKAGES
```

```shell
pip3 install -r requirements.txt
```

#### Virtualenv (Optional: Isolated Environment for Python packages)

Install Virtualenv and create an environment named `venv` (or any name you prefer) within your project directory:
```shell
pip3 install virtualenv
cd PROJECT_DIR/
virtualenv venv
```

Before installing any other packages from the project, activate the virtual environment to isolate your environment for all following commands:
```shell
source venv/bin/activate
```

If on Windows, run the script directly instead:
```
./venv/Scripts/activate
```

Run all Python and PIP commands here.

To deactivate the isolated virtual environment and return to the original environment, either close the console window or run the following command:
```shell
deactivate
```

#### Flask

Flask is installed by the PIP commands above.

For all following commands, `flask` can be replaced with `python3 -m flask` if the Flask executable is not available.

Migrate the database to the newest version:
```shell
flask db upgrade
```

Start the server with either one of the following commands:
```shell
python3 app.py

flask run
```

The server will be available on port 5000 (http://127.0.0.1:5000).

### MySQL

Install [MySQL](https://www.mysql.com/).

Configure access to the root account on MySQL so that you can login with the following command:
```
mysql -u root -p YOUR_PASSWORD_HERE
```

Exit the MySQL prompt by typing:
```
exit
```

For reference, see this [sample guide from DigitalOcean for Debian-based systems](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-18-04).

### Yarn (with React)

Install [Yarn](https://yarnpkg.com/).

Install the necessary packages:
```shell
yarn install
```

Start the server locally:
```shell
yarn start
```

The server will be available on port 3000 (http://127.0.0.1:3000).

#### Deployment

To build deployable files, edit the value `homepage` in `package.json` to be the URL where the web application will be hosted, so that the page can resolve the correct URL to its resources.

Build the files:
```shell
yarn build
```

The completed files will be ready for deployment at directory `build/`.

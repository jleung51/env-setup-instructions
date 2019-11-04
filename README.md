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

Install [Angular](https://angular.io/).

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

Install the pip dependencies:
```shell
pip3 install PACKAGES
```

```shell
pip3 install -r requirements.txt
```

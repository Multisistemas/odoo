[![Build Status](http://runbot.odoo.com/runbot/badge/flat/1/9.0.svg)](http://runbot.odoo.com/runbot)
[![Tech Doc](http://img.shields.io/badge/9.0-docs-8f8f8f.svg?style=flat)](http://www.odoo.com/documentation/9.0)
[![Help](http://img.shields.io/badge/9.0-help-8f8f8f.svg?style=flat)](https://www.odoo.com/forum/help-1)
[![Nightly Builds](http://img.shields.io/badge/9.0-nightly-8f8f8f.svg?style=flat)](http://nightly.odoo.com/)

Odoo
----

Odoo is a suite of web based open source business apps.

The main Odoo Apps include an <a href="https://www.odoo.com/page/crm">Open Source CRM</a>, <a href="https://www.odoo.com/page/website-builder">Website Builder</a>, <a href="https://www.odoo.com/page/e-commerce">eCommerce</a>, <a href="https://www.odoo.com/page/project-management">Project Management</a>, <a href="https://www.odoo.com/page/accounting">Billing &amp; Accounting</a>, <a href="https://www.odoo.com/page/point-of-sale">Point of Sale</a>, <a href="https://www.odoo.com/page/employees">Human Resources</a>, Marketing, Manufacturing, Purchase Management, ...  

Odoo Apps can be used as stand-alone applications, but they also integrate seamlessly so you get
a full-featured <a href="https://www.odoo.com">Open Source ERP</a> when you install several Apps.


Getting started with Odoo
-------------------------
For a standard installation please follow the <a href="https://www.odoo.com/documentation/9.0/setup/install.html">Setup instructions</a>
from the documentation.

If you are a developer you may type the following command at your terminal:

    wget -O- https://raw.githubusercontent.com/odoo/odoo/9.0/odoo.py | python

Then follow <a href="https://www.odoo.com/documentation/9.0/tutorials.html">the developer tutorials</a>


For Odoo employees
------------------

To add the odoo-dev remote use this command:

    $ ./odoo.py setup_git_dev

To fetch odoo merge pull requests refs use this command:

    $ ./odoo.py setup_git_review
    
Below are installation steps for both systems. Make sure that every command finishes successfully (at least doesn't report any errors).

Mac OS X El Capitan 10.11.2
---------------------------

Prerequisites: I already had git and python 2.7.10.

1) Clone odoo repository:

git clone https://github.com/odoo/odoo.git
2) Download and install Postgresapp

Go to http://postgresapp.com/, download
Open it in Finder, drag to Applications, double click
Postgres application appears, double click it
Sorry if these steps are obvious, it is just for me since I am not a Mac OS user
Now add to ~/.bash_profile:

export PATH=$PATH:/Applications/Postgres.app/Contents/Versions/latest/bin
And just execute the command above it if you already have the open terminal.

3) Install pip

sudo easy_install pip
4) Install nodejs

Go to https://nodejs.org,
Download node v4.3.0
Move to Applications, run and install
Open terminal and check that node and npm commands are available
5) Install less and less-plugin-clean-css

sudo npm install -g less less-plugin-clean-css
Should show output like this:

/usr/local/bin/lessc -> /usr/local/lib/node_modules/less/bin/lessc
less-plugin-clean-css@1.5.1 /usr/local/lib/node_modules/less-plugin-clean-css
└── clean-css@3.4.9 (source-map@0.4.4, commander@2.8.1)
less@2.6.0 /usr/local/lib/node_modules/less
├── mime@1.3.4
├── graceful-fs@3.0.8
├── image-size@0.3.5
├── errno@0.1.4 (prr@0.0.0)
├── promise@6.1.0 (asap@1.0.0)
├── source-map@0.4.4 (amdefine@1.0.0)
├── mkdirp@0.5.1 (minimist@0.0.8)
└── request@2.69.0 (aws-sign2@0.6.0, forever-agent@0.6.1, tunnel-agent@0.4.2, oauth-sign@0.8.1, is-typedarray@1.0.0, caseless@0.11.0, stringstream@0.0.5, isstream@0.1.2, json-stringify-safe@5.0.1, extend@3.0.0, tough-cookie@2.2.1, node-uuid@1.4.7, qs@6.0.2, combined-stream@1.0.5, mime-types@2.1.9, form-data@1.0.0-rc3, aws4@1.2.1, hawk@3.1.3, bl@1.0.2, har-validator@2.0.6, http-signature@1.1.1)
6) Install binary dependencies

I think not all the steps below are really necessary, but I performed them, so include just for the case they actually were needed.

Run in the terminal xcode-select --install, when dialog appears - agree to install
Go to http://brew.sh and follow instructions to install homebrew
Once you have brew, run the following in the terminal:

brew install autoconf automake libtool
brew install libxml2 libxslt libevent
7) Install python dependencies

sudo easy_install -U setuptools
pip install --user -r requirements.txt
It should show something like this at the end:

Successfully installed Babel-1.3 Jinja2-2.7.3 Mako-1.0.1 MarkupSafe-0.23 Pillow-2.7.0 PyYAML-3.11 Python-Chart-1.39 Werkzeug-0.9.6 argparse-1.2.1 beautifulsoup4-4.4.1 decorator-3.4.0 docutils-0.12 feedparser-5.1.3 gdata-2.0.18 gevent-1.0.2 greenlet-0.4.7 jcconv-0.2.3 lxml-3.4.1 mock-1.0.1 ofxparse-0.14 passlib-1.6.2 psutil-2.2.0 psycogreen-1.0 psycopg2-2.5.4 pyPdf-1.13 pydot-1.0.2 pyparsing-2.0.1 pyserial-2.7 python-dateutil-1.5 python-ldap-2.4.19 python-openid-2.2.5 python-stdnum-1.2 pytz-2013.7 pyusb-1.0.0b2 qrcode-5.1 reportlab-3.1.44 requests-2.6.0 six-1.4.1 suds-jurko-0.6 vatnumber-1.2 vobject-0.6.6 xlwt-0.7.5
8) Run odoo

cd odoo  # change dir to the folder you cloned odoo to
export LC_ALL=en_US.UTF-8
export LANG=en_US.UTF-8

# Re-check parameters, it looks like addons path you used is incorrect
./odoo.py --addons-path=addons --db-filter=mydb
Now you should see the output like this:

INFO ? openerp: OpenERP version 9.0c
INFO ? openerp: addons paths: ['/Users/dev/Library/Application Support/Odoo/addons/9.0', u'/Users/dev/projects/odoo/addons', '/Users/dev/projects/odoo/openerp/addons']
INFO ? openerp: database: default@default:default
INFO ? openerp.service.server: HTTP service (werkzeug) running on 0.0.0.0:8069
9) Open odoo in your browser

Go to http://localhost:8069
The database setup window appears (see the first screenshot below)
Enter databse name = mydbodoo (I think the prefix mydb is important here) and password admin
You can also check the checkbox to load the demo data
Click Create database
Wait and you should be redirected to the odoo interface (see the second screenshot)
Done!

Odoo databse setup

Odoo user interface

Update: Mac OS X El Capitan 10.11.2 with virtualenv

Do the same as above, on step (7) do not run pip install --user -r requirements.txt and instead to this:

pip install virtualenv  # not sure here, sudo may be needed
mkdir ~/venv
cd ~/venv
mkdir odoo
virtualenv odoo
source ~/venv/odoo/bin/activate
cd ~/path/to/odoo
pip install -r requirements.txt  # no sudo here!
Now continue with step (8). Each time, before starting odoo make sure to activate the virtualenv first:

source ~/venv/odoo/bin/activate
export LC_ALL=en_US.UTF-8
export LANG=en_US.UTF-8

./odoo.py --addons-path=addons --db-filter=mydb
Ubuntu 15.04

Prerequisites: I already had postgresql 9.4.5, nodejs 0.10.25 and python 2.7.8.

Installation:

git clone https://github.com/odoo/odoo.git 
cd odoo
sudo apt-get install libldap2-dev libsasl2-dev libevent-dev libxslt1-dev libxml2-dev 
pip install -r requirements.txt
sudo npm install -g less less-plugin-clean-css
./odoo.py --addons-path=addons --db-filter=mydb
That's all, now setup the same way as in the step (9) for Mac OS.


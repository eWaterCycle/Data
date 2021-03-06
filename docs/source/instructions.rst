Instructions
------------

Register at Copernicus Climate Data Service
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  You have to register at Copernicus Climate Data Service:
   `copernicus <https://cds.climate.copernicus.eu/user/register?destination=%2F%23!%2Fhome>`__.
   After activating your account use your new account to log in. In you
   profile page you can find your user ID and your API key.

-  Copy your user ID and API key.

Create a key ascii file
~~~~~~~~~~~~~~~~~~~~~~~

Linux
#####
In Linux create a new file called .cdsapirc in the home directory of your user and add the following two lines:

::

   url: https://cds.climate.copernicus.eu/api/v2

   key: UID:KEY

Replace UID with your user ID and KEY with your API key

Windows
#######
In Windows create a new file called .cdsapirc (e.g. with Notepad) where in your windows environment, %USERPROFILE% is usually located at C:\Users\Username folder). And add the following two lines

::

   url: https://cds.climate.copernicus.eu/api/v2

   key: UID:KEY

Replace UID with your user ID and KEY with your API key

MacOS
#####
In MacOS create a new file called .cdsapirc in the home directory of your user and add the following two lines:


::

   url: https://cds.climate.copernicus.eu/api/v2

   key: UID:KEY

Replace UID with your user ID and KEY with your API key

Info on available variables
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. argparse::
   :module: era5cli.cli
   :func: _build_parser
   :prog: era5cli
   :path: info

Tip: search in variables
########################

To quickly search the list of variables for a specific word, you can use the
built-in ``grep`` command. For example:

::

   era5cli info "2Dvars" | grep temperature


should list all single level variables that contain the word 'temperature', so
they can be easily identified for an era5cli request.

Running era5cli from the command line
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
era5cli can be used to fetch both hourly data and monthly averaged data.

Fetching hourly data
####################

Fetch hourly data through an cdsapi call via command line. More information on the available data and options can be found on:

| `Era5 hourly single levels download page <https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-single-levels>`_.
| `Era5 hourly pressure levels download page <https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-pressure-levels>`_.
| `Era5 hourly single levels preliminary back extension download page <https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-single-levels-preliminary-back-extension>`_.
| `Era5 hourly pressure levels preliminary back extension download page <https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-pressure-levels-preliminary-back-extension>`_.
| `Era5-Land hourly download page <https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-land>`_.


.. argparse::
   :module: era5cli.cli
   :func: _build_parser
   :prog: era5cli
   :path: hourly


Fetching monthly data
#####################

Fetch monthly data through an cdsapi call via command line. More information on the available data and options can be found on:

| `Era5 monthly single levels download page <https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-single-levels-monthly-means>`_.
| `Era5 monthly pressure levels download page <https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-pressure-levels-monthly-means>`_.
| `Era5 monthly single levels preliminary back extension download page <https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-single-levels-monthly-means-preliminary-back-extension>`_.
| `Era5 monthly pressure levels preliminary back extension download page <https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-pressure-levels-monthly-means-preliminary-back-extension>`_.
| `Era5-Land monthly download page <https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-land-monthly-means>`_.


For the monthly data, some of the variables are not available. Exceptions on the single level data can be found in table 8 of
`ERA5 parameter listings <https://confluence.ecmwf.int/display/CKB/ERA5+data+documentation#ERA5datadocumentation-Parameterlistings>`_

.. argparse::
   :module: era5cli.cli
   :func: _build_parser
   :prog: era5cli
   :path: monthly


Removing or canceling requests
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

ERA-5 download requests will be saved in the `Your requests <https://cds.climate.copernicus.eu/cdsapp#!/yourrequests>`_ section in your profile on the Copernicus Climate Data Store. Here you can re-download the requested data, cancel active requests, or remove old requests.

Note that it is currently not possible to cancel active requests from the command line: Killing the process will not download the data to your local machine but still add it to your Copernicus account.

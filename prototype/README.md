# SPICE Ephemeris Search

The goal of this prototype is to return ephemeris data for item requested.

Kernels will have to be supplied.

This is a test to try and get query data from SPICE based on a python app.

### Set up Python Development Environment using virtualenv
In a development environment, make sure you have the following:
```
python3
pip3
virtualenv
```
Steps:

1. To install virtualenv
   ```
   pip3 install --user virtualenv
   ```
1. Set up virtualenv venv
   ```
   python3 -m virtualenv venv
   ```
1. Go into the virtualenv (defaults to bash, use appropriate source file for other shells):
   ```
   source venv/bin/activate
   ```
You can now program in python installing requirements specific to your program without affecting the entire system.


### Install `requirements.txt`
```
pip3 install -r requirements.txt
```

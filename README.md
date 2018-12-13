# Quahog Quaick Start

## Transferring Files to Quahog

### Setting up ampy

Install virtualenv

> apt-get install virtualenv

Create a virtualenv

> virtualenv venv

Activate it

> source venv/bin/activate

Install ampy in virtualenv

> pip install adafruit-ampy

Check which USB port you've got your Quahog on (in most cases, this will be /dev/ttyUSB0).

> ls /dev/ttyUSB*


(Note: in the following, you may need to use 'sudo'; I believe that the latest versions of Ubuntu require this.)







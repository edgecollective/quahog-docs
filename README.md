# Quahog Quaick Start

On Ubuntu:

## Transferring Files to/from Quahog

### Setting up ampy (file transfer utility)

Install virtualenv

``` 
apt-get install virtualenv
```

Create a virtualenv

``` 
virtualenv venv
``` 

Activate it

``` 
source venv/bin/activate
``` 

Install ampy in virtualenv

``` 
pip install adafruit-ampy
``` 

Check which USB port you've got your Quahog on (in most cases, this will be /dev/ttyUSB0).

``` 
ls /dev/ttyUSB*
``` 

### Using ampy to transfer files

(Note: in the following, you may need to use 'sudo'; I believe that the latest versions of Ubuntu require this.)

- Listing files on the Quahog

``` 
ampy -p /dev/ttyUSB0 ls
``` 

- Putting a file on the Quahog

``` 
ampy -p /dev/ttyUSB) put ./foo.py
``` 

- Getting a file from the Quahog

``` 
ampy -p /dev/ttyUSB0 get foo.py
``` 

- Getting a file from the Quahog and piping it into a local file

``` 
ampy -p /dev/ttyUSB0 get foo.py > ./myfoo.py
``` 

## Connecting to the Micropython REPL

Install screen

``` 
apt-get install screen
``` 

Connect to Quahog. (Note: in the following, you may need to use 'sudo'; I believe that the latest versions of Ubuntu require this.)

``` 
screen /dev/ttyUSB0 115200 
``` 

You should see a REPL prompt

``` 
>>>
``` 

You can now use the Python REPL.  For example, to list files on the device:

``` 
>>> import os
>>> os.listdir()
``` 

To exit 'screen', type:  Ctrl-a \

## Using the Quahog with FarmOS

This repo has a python script, located in the 'farmos/' directory, called 'farmos_post_dht22.py'. 

Below, we'll use this file to post DHT22 sensor temp and humidity values to FarmOS.

First, modify farmos_post_dht22.py to use your FarmOS publickey and private key.  Also, add your wifi credentials.

Then, upload the script to your Quahog

``` 
ampy -p /dev/ttyUSB0 put farmos_post_dht22.py
```

Now we can 'screen' into the Quahog and run the script:

``` 
screen /dev/ttyUSB0 115200
>>> import farmos_post_dht22
```

Note: if you would like this script to run on Quahog startup, copy it into a file called 'main.py', and put this on your board using ampy.








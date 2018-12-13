# Quahog Quaick Start

## Transferring Files to/from Quahog

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

### Using Ampy

(Note: in the following, you may need to use 'sudo'; I believe that the latest versions of Ubuntu require this.)

- Listing files on the Quahog

> ampy -p /dev/ttyUSB0 ls

- Putting a file on the Quahog

> ampy -p /dev/ttyUSB) put ./foo.py

- Getting a file from the Quahog

> ampy -p /dev/ttyUSB0 get foo.py

- Getting a file from the Quahog and piping it into a local file

> ampy -p /dev/ttyUSB0 get foo.py > ./myfoo.py

## Connecting to the Quahog REPL

Install screen

> apt-get install screen

Connect to Quahog. (Note: in the following, you may need to use 'sudo'; I believe that the latest versions of Ubuntu require this.)

screen /dev/ttyUSB0 115200 

You should see a REPL prompt

> >>>

To exit 'screen':  Ctrl-a \





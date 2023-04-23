# jetson_sphero

Applications to run on Nvidia Jetson Nano mounted on a Sphero RvR

The code procedure to get things running was adapted (copied) from here: [Sparkfun - Jetson Hacks](https://learn.sparkfun.com/tutorials/jetson-nano--sphero-rvr-mash-up-part-2/all#the-hacked-sphero-rvr-sdk)

The Sphero SDK in this repo is the latest version I could find for the Raspberry PI and I adapted it to work with the Nano. If you wand to download another version of the Sphero SDK see [this](#adapt-anaother-version-of-sphero-sdk).

After cloning this repo:

- you need to change direcory into ```sphero-sdk-nano-python``` folder:

    ``` bash
    cd sphero-sdk-nano-python
    ```

- install the SDK:

    ``` bash
    sudo python3 setup.py install
    ```

- if you get errors you may need to create a virtual environment with [venv](https://docs.python.org/3/library/venv.html) and install the sdk there. Note that if you use the venv the install command does **NOT** have ```sudo```

To get started with examples on how to control the Sphero, head to:

``` bash
cd sphero-sdk-nano-python/getting_started/observer/driving
```

I suggest looking and reading the main comments of ```control_system_selection.py``` file first.

**Notes:**

Make sure to change the permisions of /dev/ttyTHS1 (if 666 does not work try 777):

``` bash
sudo chmod 666 /dev/ttyTHS1
```

## Adapt anaother version of Sphero SDK

The steps to make your own Sphero-Nano SDK are simple:

- clone the official Sphero SDK from [here](https://github.com/sphero-inc/sphero-sdk-raspberrypi-python)
- open the project in a code editor that supports finding text code in all files (ex: VSCode)
- search for ALL (ctrl+shift+f in VSCode) ```/dev/ttyS0``` and replace with ```/dev/ttyTHS1```
- install the Sphero SDK with ```sudo python3 setup.py install```

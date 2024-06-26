.. _install-linux:

####################
Installation - Linux
####################

^^^^^^^^^^^^^
Prerequisites
^^^^^^^^^^^^^

* Vector is powered on.
* Vector has been set up with wire-pod.
* Vector is connected to the same network as your computer.
* You can see Vector's eyes on his screen.


This guide provides instructions on installing the Vector SDK for computers running with an Ubuntu Linux operating system.

.. warning:: The Vector SDK is tested and and supported on Ubuntu 22.04. Anki makes no guarantee the Vector SDK will work on other versions of Linux.  If you wish to try the Vector SDK on versions of Linux *other than* Ubuntu 22.04, please ensure the following dependencies are installed:

  * Python 3.9 or later
  * pip for Python 3 (Python package installer)



^^^^^^^^^^^^
Ubuntu 22.04
^^^^^^^^^^^^

"""""""""""""""""""
Python Installation
"""""""""""""""""""

1. Type the following into your Terminal window to install Python::

    sudo apt-get update
    sudo apt-get install python3

2. Then install pip by typing in the following into the Terminal window::

    sudo apt install python3-pip

3. Last, install Tkinter::

    sudo apt-get install python3-pil.imagetk

"""""""""""""""""""""""""""""""""""""""""""""""""""""""
SDK Installation - Ubuntu 22.04 (Python 3.10 and below)
"""""""""""""""""""""""""""""""""""""""""""""""""""""""

If you have any other Vector SDK installed, uninstall it by running these commands in the Terminal window::

    python3 -m pip uninstall -y anki_vector
    python3 -m pip uninstall -y ikkez_vector
    python3 -m pip uninstall -y cyb3r_vector_sdk

To install the SDK, type the following into the Terminal window::

    python3 -m pip install --user wirepod_vector_sdk

If you want to use the 3D viewer, type the following as well::

    python3 -m pip install --user wirepod_vector_sdk[3dviewer]

Now move on to Vector Authentication.

"""""""""""""""""""""""""""""""""""""""""""""""""""""
SDK Installation - Arch Linux (Python 3.11 and above)
"""""""""""""""""""""""""""""""""""""""""""""""""""""

If you have any other Vector SDK installed, uninstall it by running these commands in the Terminal window::

    python3 -m pip uninstall --break-system-packages -y anki_vector
    python3 -m pip uninstall --break-system-packages -y ikkez_vector
    python3 -m pip uninstall --break-system-packages -y cyb3r_vector_sdk

To install the SDK, type the following into the Terminal window::

    python3 -m pip install --break-system-packages --user wirepod_vector_sdk

If you want to use the 3D viewer, type the following as well::

    python3 -m pip install --break-system-packages --user wirepod_vector_sdk[3dviewer]

Now move on to Vector Authentication.

"""""""""""
SDK Upgrade
"""""""""""

To upgrade the SDK from a previous install, enter this command::

    python3 -m pip install --break-system-packages --user --upgrade wirepod_vector_sdk

^^^^^^^^^^^^^^^^^^^^^
Vector Authentication
^^^^^^^^^^^^^^^^^^^^^

First, in case it exists, make sure your .anki_vector folder is accessible by the user. To do this, type the following commands into the Terminal window. It may ask for your password. Note that as a security measure, your password will not show up as you are typing it::
    
    sudo chmod +rwx ~/.anki_vector
    sudo chown -R $USER ~/.anki_vector

To authenticate with the robot, type the following into the Terminal window::

    python3 -m anki_vector.configure

You will be prompted for your robot's name, ip address and serial number. You will also be asked to provide the IP address of your wire-pod instance. You can have it try to find the instance automatically if that is more convenient.

You will see "SUCCESS!" when this script successfully completes.

.. note:: By running the ``anki_vector.configure`` executable submodule, you will be asked to provide the IP address of your wire-pod instance (you can also have the script automatically try to find the wire-pod instance), and the script will automatically download an authentication token and certificate to your computer that will grant you access to the robot and his capabilities (such as camera and audio) as well as data stored on the robot (such as faces and photos).

  The downloaded access token is equivalent to your account credentials. It will be stored in your user directory (~/.anki_vector) along with a robot identity certificate and other useful data for establishing a connection. Do not share your access token.

.. warning:: These credentials give full access to your robot, including camera stream, audio stream and data. Do not share these credentials.



^^^^^^^^^^^^^^^
Troubleshooting
^^^^^^^^^^^^^^^

Please see the :doc:`Troubleshooting </troubleshooting>` page for tips, or visit the `Unofficial DDL Discord <https://discord.gg/Hs4QuhDush>`_ to ask questions, find solutions, or for general discussion.

----

Anki, modified by kercre123


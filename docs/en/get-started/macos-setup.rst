**********************************************
Standard Setup of Toolchain for Mac OS
**********************************************

:link_to_translation:`zh_CN:[中文]`

Install Prerequisites
=====================

ESP-IDF will use the version of Python installed by default on macOS.

- install pip::

    sudo easy_install pip

- install CMake & Ninja build:

  - If you have HomeBrew_, you can run::

      brew install cmake ninja dfu-util

  - If you have MacPorts_, you can run::

      sudo port install cmake ninja dfu-util

  - Otherwise, consult the CMake_ and Ninja_ home pages for macOS installation downloads.

- It is strongly recommended to also install ccache_ for faster builds. If you have HomeBrew_, this can be done via ``brew install ccache`` or ``sudo port install ccache`` on MacPorts_.

.. note::
   If an error like this is shown during any step::

     xcrun: error: invalid active developer path (/Library/Developer/CommandLineTools), missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun

   Then you will need to install the XCode command line tools to continue. You can install these by running ``xcode-select --install``.

Installing and setting up Python 3 as default
---------------------------------------------

Basing on macOS `Catalina 10.15 release notes`_, use of Python 2.7 is not recommended and Python will not be included by default in future versions of macOS. Check what Python you currently have::

  python --version

If the output is like ``Python 2.7.17``, your default interpreter is Python 2.7. If so, also check if Python 3 isn't already installed on your computer::

  python3 --version

If above command returns an error, it means Python 3 is not installed. 

Below is an overview of steps to install Python 3 and making it default interpreter. 

  - Installing with HomeBrew_ can be done as follows::

      brew install python3
      ln -s /usr/local/bin/python3.8 /usr/local/bin/python

    Adjust above directory name ``/usr/local/bin/python3.8`` to point where Python 3 has been installed. To check this directory you can run  ``which -a python``.

  - If you have MacPorts_, you can run::

      sudo port install python38
      sudo port select --set python python38

Now open a new terminal session to verify what python is running by default::

  python --version

If the output is similar to ``Python 3.8.5``, your installation has been done successfully.


.. note::

    This is system-wide change which may affect all of the applications.

Next Steps
==========

To carry on with development environment setup, proceed to :ref:`get-started-get-esp-idf`.


.. _cmake: https://cmake.org/
.. _ninja: https://ninja-build.org/
.. _ccache: https://ccache.samba.org/
.. _homebrew: https://brew.sh/
.. _MacPorts: https://www.macports.org/install.php
.. _Catalina 10.15 release notes: https://developer.apple.com/documentation/macos-release-notes/macos-catalina-10_15-release-notes

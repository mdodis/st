# st - simple terminal
--------------------
st is a simple terminal emulator for X which sucks less.


## Requirements
------------
In order to build st you need the Xlib header files.


## Installation
------------
Edit config.mk to match your local setup (st is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install st (if
necessary as root):

    make clean install


## Running st
----------
If you did not install st with make clean install, you must compile
the st terminfo entry with the following command:

    tic -sx st.info

See the man page for additional details.

### Setting st as the default terminal emulator
-------------------------------------------
On debian systems, run sudo make install-alternatives (x-terminal-emulator change)

If you're using nautilus (it uses a hardcoded list of terminals, 
and st is not one of them), a simple hack would be to add this is your ~/.bashrc file:

``` bash
if ps -o cmd= -p $(ps -o ppid= -p $$) | grep -q gnome; then
  nohup st &> /dev/null &
  sleep 0.1s
  exit
fi
```

Credits
-------
Based on Aurélien APTEL <aurelien dot aptel at gmail dot com> bt source code.


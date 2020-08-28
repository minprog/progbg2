
## Python version

There are different versions of Python, in this course you have to use
version 3.5 or higher. To see what version you are using type in a
shell/terminal:

    $ python --version

If you have a version 3.5 or higher you can skip to the next section,
otherwise continue reading. On some operating systems there are
multiple versions of python available, for example:

    $ python3 --version

You can create a python environment to always use the correct version
of python and related tools like 'pip':

    $ python3 -m venv ~/python3_env

To activate this environment type:

    $ source ~/python3_env/bin/activate

And to deactive it type:

    $ deactivate

To make sure this python3 environment is always activated on Ubuntu
when you start a shell (so you won't forget), you can add the
activation to your Bash startup file by once running (this appends to
file ~/.bashrc):

    $ echo -e "\n# activate python3 environment:\nsource ~/python3_env/bin/activate" >> ~/.bashrc

If you are on Mac OS, you probably also need to run this once (this
appends to file ~/.bash_profile):

    $ echo -e "\n# source .bashrc:\nif [ -r ~/.bashrc ]; then\n  source ~/.bashrc\nfi" >> ~/.bash_profile

Start a new shell and check if it works! Using an old version will
cause problems later.

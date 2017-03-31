jdl2makeflow
============

Run [AliEn](http://alien.web.cern.ch) JDLs on multiple platforms using
[Makeflow](http://ccl.cse.nd.edu/software/makeflow).


Requirements
------------
[Makeflow](http://ccl.cse.nd.edu/software/makeflow) needs to be installed on
your system. Makeflow is part of the Cooperative Computing tools (cctools). To
install it, [download the latest
version of cctools](http://ccl.cse.nd.edu/software/downloadfiles.php) then
unpack, compile and install it (we are assuming 6.1.1 is the latest, check the
download page first):

    cd /tmp
    curl -L http://ccl.cse.nd.edu/software/files/cctools-6.1.1-source.tar.gz | tar xzf -
    cd cctools-*-source/
    ./configure && make -j10
    sudo make install

Run the last command (`make install`) *as root* to install it system-wide.
Adjust `-j10` to the number of parallel cores you want to use during the build.
If you do not have root privileges:

    cd /tmp
    curl -L http://ccl.cse.nd.edu/software/files/cctools-6.1.1-source.tar.gz | tar xzf -
    cd cctools-*-source/
    ./configure --prefix=$HOME/cctools && make -j10 && make install
    echo 'export PATH=$HOME/cctools/bin:$PATH' >> ~/.bashrc
    echo 'export LD_LIBRARY_PATH=$HOME/cctools/bin:$LD_LIBRARY_PATH' >> ~/.bashrc

We are installing under `~/cctools` but you can use the directory you want.
Also, we are assuming your shell configuration file is `~/.bashrc`, adjust it
according to your shell.


Get jdl2makeflow
----------------

As easy as:

    sudo pip install alien_jdl2makeflow

If you cannot install it as root, you will probably have to export some Python
variables to make it work. If you have a user installation of some Python
distribution like [Anaconda](https://www.continuum.io/downloads) this is
probably already done for you.



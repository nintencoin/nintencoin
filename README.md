nintencoin integration/staging tree
================================

http://www.nintencoin.com

Copyright (c) 2009-2013 Bitcoin Developers
Copyright (c) 2011-2013 Litecoin Developers
Copyright (c) 2014 ninten coin Developers

What is ninten coin?
----------------

ninten coin is a version of Litecoin and uses scrypt as a proof-of-work algorithm.
 - 1 minute block targets
 - Subsidy is static at 31709 ninten coins per block
 - 100 billion total coins
 - 1 hour to retarget difficulty
 
How to build on Linux

1). Install all necessary dependencies
> sudo apt-get update
> sudo apt-get install sudo apt-get install build-essential libboost-all-dev
> sudo apt-get install libcurl4-openssl-dev libdb5.1-dev libdb5.1++-dev git qt-sdk libminiupnpc-dev
> sudo apt-get install python-software-properties screen git python-rrdtool python-pygame python-scipy 
> sudo apt-get install python-twisted python-twisted-web python-imaging build-essential libglib2.0-dev libglibmm-2.4-dev 
> sudo apt-get install python-dev libboost-all-dev libdb++-dev autoconf automake ncurses-dev
> sudo apt-get install qttools5-dev-tools
> sudo apt-get install libminiupnpc-dev

2). Download the latest sources for ninten coin from github
> git clone https://github.com/nintencoin/nintencoin.git

3.1). Build ninten coin daemon
> cd nintencoin/src
> make -f makefile.unix
> strip nintencoind

3.2). Run ninten coin daemon
> ./nintencoind

4.1). Build ninten coin qt piggy bank
> cd nintencoin
> qmake bitcoin-qt.pro
> make

4.2). Run qt piggy bank
> ./nintencoin-qt

----------------

For more information, as well as an immediately useable, binary version of
the ninten coin client sofware, see http://www.nintencoin.com.

License
-------

nintencoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.

Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the nintencoin
development team members simply pulls it.

If it is a *more complicated or potentially controversial* change, then the patch
submitter will be asked to start a discussion (if they haven't already) on the
[mailing list](http://sourceforge.net/mailarchive/forum.php?forum_name=bitcoin-development).

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see `doc/coding.txt`) or are
controversial.

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/bitcoin/bitcoin/tags) are created
regularly to indicate new official, stable release versions of nintencoin.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test. Please be patient and help out, and
remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write unit tests for new code, and to
submit new unit tests for old code.

Unit tests for the core code are in `src/test/`. To compile and run them:

    cd src; make -f makefile.unix test

Unit tests for the GUI code are in `src/qt/test/`. To compile and run them:

    qmake BITCOIN_QT_TEST=1 -o Makefile.test bitcoin-qt.pro
    make -f Makefile.test
    ./nintencoin-qt_test



	
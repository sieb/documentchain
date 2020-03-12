# setup dms wallet on raspbian

Dependencies:

`sudo apt-get install curl build-essential libtool autotools-dev automake pkg-config python3 bsdmainutils cmake screen`

`git clone https://github.com/Krekeler/documentchain.git`

what's the host-plataform-triplet?
`gcc -dumpmachine`
something like `arm-linux-gnueabihf` for raspbian!

 * Please replace `<host>` with your local system's `host-platform-triplet`. The following triplets are usually valid:

`arm-linux-gnueabihf` for Linux ARM 32 bit (All Raspbian generic)

`aarch64-linux-gnu` for Linux ARM 64 bit

`i686-linux-gnu` for Linux Intel86 32 bit 

`x86_64-linux-gnu` for Ubuntu 18.04 AMD

cd depends and `make HOST=host-platform-triplet -j4` ; your own hpt!

cd .. `./autogen.sh` ;

./configure --prefix `pwd`/depends/<host> ; host is just your own hpt

`make`

***
Simplified:

 * __My owner workflow__:
 
 1 - cd depends and `make HOST=arm-linux-gnueabihf -j4` ;
 
 2 - cd .. `./autogen.sh` ;
 
 3 - `./configure --prefix `pwd`/depends/arm-linux-gnueabihf` 
 
 4 - `make`

The binaries generated in src directory.

<h1>Tutorial - Install node on Ubuntu Server 18.04</h1>
<br/><br/>
Install a node for your coin on Ubuntu Server 18.04 with the following tutorial.
<br/><br/>
Update your Ubuntu server with the following command:<br/>
sudo apt-get update && sudo apt-get upgrade -y
<br/><br/>
Install the required dependencies with the following command:<br/>
 sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils python3 libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-test-dev libboost-thread-dev libboost-all-dev libboost-program-options-dev libminiupnpc-dev libzmq3-dev libprotobuf-dev protobuf-compiler unzip software-properties-common cmake -y
<br/><br/>
Install BLS signatures with the following commands:<br/>
cd ~/<br/>
wget https://github.com/codablock/bls-signatures/archive/v20181101.zip<br/>
unzip v20181101.zip<br/>
cd bls-signatures-20181101<br/>
cmake .<br/>
sudo make install
<br/><br/>
Type the following command to go back to your home directory:<br/>
cd $HOME
<br/><br/>
Install the repository ppa:bitcoin/bitcoin with the following command:<br/>
sudo add-apt-repository ppa:bitcoin/bitcoin
<br/><br/>

Confirm the installation of the repository by pressing on the enter key: enter
<br/><br/>
Install Berkeley DB with the following command:<br/>
sudo apt-get update && sudo apt-get install libdb4.8-dev libdb4.8++-dev -y
<br/><br/>

Download the Linux daemon for your wallet with the following command:<br/>
git clone https://github.com/costaricadigitalcoin/cococr-linux-daemon.git cococr
<br/><br/>

Change of directory:<br/>
cd cococr
<br/><br/>

Change permissions, paste this command and press the key: enter<br/>
chmod +x cococostaricad cococostarica-cli cococostarica-tx 
<br/><br/>

Type the following command to install the daemon and tools for your wallet:<br/>
sudo mv cococostaricad cococostarica-cli cococostarica-tx /usr/bin/
<br/><br/>

Create the data directory for your coin with the following command:<br/>
mkdir $HOME/.cococostarica
<br/><br/>

Open nano:<br/>
nano $HOME/.cococostarica/cococostarica.conf -t
<br/><br/>

Paste the following into nano:<br/>
rpcuser=rpc_cococostarica<br/>
rpcpassword=dR2oBQ3K1zYMZQtJFZeAerhWxaJ5Lqeq9J2<br/>
rpcallowip=127.0.0.1<br/>
listen=1<br/>
server=1<br/>
txindex=1<br/>
daemon=1<br/>
<br/>
Save the file with the keyboard shortcut ctrl + x.
<br/><br/>
Type the following command to start your node:<br/>
cococostaricad

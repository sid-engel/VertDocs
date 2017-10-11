## What Is P2Pool?
Think of P2Pool as a mining pool, for Bitcoin, Litecoin, Vertcoin, and other crypto-currencies… Just, with a twist. People can create nodes, which are pretty much sub-pools. This allows people with small hashing power, to run their own “pool” like environment, and get paid out per share(like a standard pool).

## Why You Should Create Your Own
Running your own node(on the network of your rigs), gives you a 0ms delay to the pool. This means, your rig can receive, and send off shares, as fast as possible. Believe it or not, this makes a massive difference, and will impact your profitability/ROI for the better.

Another big attraction, is the fact that running your own node allows you to bypass any pool/nodes(owned by other people) fees that you would normally be forced to work within. Your standard pool now-a-days, charges around 1%. It’s not a significant increase in profitability, but every last bit counts. I think, at least.

There’s no downside to running one(while it’s local), and seems to be a no-brainer for Bitcoin, Litecoin, and Vertcoin miners around the globe.

## How To Do It
Hopefully, you can hang in through this how-to, and get everything working. If not, that’s what google is for. Sorry. This is all suggesting you are running on Windows.

### VertCoin Core Configuration

You need to create a wallet for the pool to use. This wallet will receive the profit from fees(if any are set… I’d go ahead and guess no). This can easily be done by going to  “C:/Users/Username/Appdata/Roaming/Vertcoin”, and creating a “vertcoin.conf” text file.

Within the file you will need to add:
server=1
rpcuser=node
rpcpassword=youreamazingsecurepassword

Suggesting this step is complete, and your wallet is done syncing with the blockchain(leave it open for a few hours). You can move on to installing the dependencies for P2Pool.

### P2Pool Dependencies(in order)

These are all pretty easy to install, I’m going to guess you can get this on your own.

* Install Python 2.7: http://www.python.org/getit/
* Install Twisted: http://twistedmatrix.com/trac/wiki/Downloads
* Install Zope.Interface: http://pypi.python.org/pypi/zope.interface/3.8.0
* Install python win32 api: http://sourceforge.net/projects/pywin32/files/pywin32/Build%20218/
* Install python win32 api wmi wrapper: https://pypi.python.org/pypi/WMI/#downloads
* Make sure to save the files into “C:\Python27\Lib\site-packages”, so Python can actually access them.
* P2Pool, obviously: https://github.com/vertcoin/p2pool-vtc

### Getting The Node Started

First off, make sure you have the Vertcoin Core wallet, running. It’s needed in order for P2Pool to function.

After unzipping the contents of P2Pool from github, you’ll see a file named “Start P2Pool.bat”. You need to edit it, so it contains the following:

“run_p2pool.exe –net vertcoin2 node youreamazingsecurepassword”

Use "vertcoin2" if you have less than 100mh/s. Otherwise, just use "vertcoin".

By default, 1% of your profits go to the dev team. But, you’re greedy right? Or is it just me, whoops. Anywho, you can add “–give-author 0” to the end of your .bat, to remove all fees.

Run your new .bat file.

Tada!

### Connecting To Your Node
Now that we have the thing running, we should probably do something with it.

Point your mining software toward “stratum+tcp://localhost:9181”.

If you want to view web-stats, which surely you will… You can view them via http://localhost:9181.

Bazinga! You’re done!

### Making Your Node Global(optional)

Now, let’s say you want to make it so your friend down the street can mine on your node. You’re gonna have to open it up to the world-wide-web!

You can accomplish the WAN showcasing of your node, simply by forwarding ports: 9181, and 9346.

From here, your node will be viewable and accessible from anywhere in the world using your ip address, instead of localhost.

## The Risks Of Running A Global Node

By running a globally accessible node, you’re opening up ports on your router. No matter what port you open, you’re inviting possible risk of someone worming some kind of way through your network, and it’s connected devices. You should do you’re research, and find out how to port forward safely before spreading word of your new node to the world.

## Extra
Source: https://sidengel.com/blog/set-p2pool-node/

Easy YouTube Tutorial: https://www.youtube.com/watch?v=CE9kGh-gGnI

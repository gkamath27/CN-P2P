# CN-P2P

Goal:
--------------

To implement a basic peer-to-peer (p2p) file sharing service in C using command line input using sockets. 

The system has two components:

• A central indexing server. This server is responsible for maintaining a list of
active peers and their list of files.
• A peer. A peer must be at the same time a client (for registering, searching and downloading files) and a server (for serving files). The peer should be able to connect to the central server for registration, listing and searching for files, and then connecting directly to another peers for transferring a file. 

The peer shell commands are: 

• **registerPeer &lt;servername&gt;** – registers the current host as a peer for the p2p system whose index server is given by the argument;  
• **unregisterPeer &lt;servername&gt;** – unregisters the current host as a peer for the p2p system whose index server is given by the argument;  
• **registerFile &lt;servername&gt; &lt;filepath&gt;** – registers the file with a given path with a given index server;  
• **unregisterFile &lt;servername&gt; &lt;filename&gt;** – unregisters the file with a given name with a given index server;  
• **listPeers &lt;servername&gt;** – lists all peers registered in the index server;  
• **listFiles &lt;servername&gt;** – lists all files available in all the peers as viewed by the index server;  
• **searchFile &lt;servername&gt; &lt;filename&gt;** – searches for a file with the indicated name, in the given index server, and lists the hosts that have it.  
• **downloadFile &lt;servername&gt; &lt;filename&gt; &lt;destdir&gt;** – downloads the file indicated by the first argument to the directory indicated by the second argument, from the peer indicated as the third argument. In the downloadFile command the index server must choose an appropriate peer to provide the file. 

The file transfer is done using a direct connection between the client and the selected peer, without further intervention from the server. 

The server is non-blocking and supports several client connections at the same time.

# Darknet

I've been fixated on how to make something like the darknet from Daemon (better reference for book here).

The key attributes of the darknet was it was distributed in execution, control and storage.  This distribution was redundant so the termination of any one node would not stop the darknet.  It was also encrypted and meshed (is that a term?).

To achieve some of these attributes, I'm looking to combine a few of my favorite technologies.

1. CJDNS (link)
2. IPFS (link)
3. tuple-space parallel programs. (link)

CJDNS is already a huge meshnetwork with privacy in mind.  It allows computers to communicate in privacy over a resilliant mesh network and is most importantly agnostic to how the links are made.  The deveopment network, Hyperboria, is mostly over Internet tunnels, but is easily made with physical/wireless adhoc etc.

IPFS - Inter Planetary File System

This is a slick project that tries to make data and the "web" permanent.  What I find interesting is that every file is indexed by it's hash, and can be found over a torrent like network by this hash.  I see this as a means to distribute code over low-rate communication, "run this program <hash>" 

Tuple-space - David G.
This is my prefered way to write parallel programs.  It's an asyncronyous message space, that passes tasks via patterns/tuples.  The downside is the architecture is centralized around the tuple-server.  This serever is light-weight but still a single point of failure.  I want to play with a distributed tuplespace, something where each darknet node runs a tupleserver with listeners monitoring adjacent tuple-servers in the darkenet (cjdns).  Whenever a task message is posted, the listener will decrement a counter and duplicate the task in host tuple space.  The goal is to spread the task over a finite but fractal map of the darkenet.

Still a lot of details to work out, but I feel like this might be an intersting progject.

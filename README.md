docker-freelan-node
===================

The base "easy to install node"

This node will have an initialise script which will do the following when called with the first one liner the user will have to type:
 
 * Uses environmental variable for location of certificate authority (ca)
 * Create certificate and send it off for signing accompanied by ca defined auto-sign network password (also environmental variable)
 * Clone the git repositories which document the static ips and ports of supernodes on the network along with the privliged nodes
   * uses environmental variable for the locations of these repos -- makes it so the image can be initialised with a one liner
 * Creates the freelan config file based on the available supernodes
 * creates ssh keys, sets up ssh server
 * Exchanges keys with currently available privilged nodes

User will then save this initialised docker image locally -- a second one liner for user to call docker with

User will then boot their unique node -- the third and final one liner the user will need to do

Periodically will
 * Do a git pull in case more supernodes or privliged users have been added
 * Update freelan config file with new supernodes
 * Do key swap with all of the not before seen priviliged nodes for no-password ssh (so the privliged nodes can run IPython engines)

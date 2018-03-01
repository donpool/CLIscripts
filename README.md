# CLIscripts

This is a Command Line Interface scripts, mostly bash ones, for various utility purposes. You can clone this into your ~/bin directory, so you can run them from any location in your PC, or you can clone the scripts individually according to your needs. 

## Scripts

* 192.168

    This script allows to connect to a remote host in the script-name prefix network (**192.168** in this case). You can rename (or ln link it) to use it in other subnets. So script will use first two octets from the script-name itself and at least one param to construct the final destination address to connect to, and altenatively a username (root by default). I.e:
    
    Usage:
        192.168 <OCTET> [octet] [user]
        Where:
        <OCTET> is the 4th octet of the destination address if no other params where provided. (Default 3th octect is "100", but configurable in the first lines of the script, in addition to "root" as username)
                is the 4th octet of the destination address if the 2nd param is not numeric, which will be assumed as a username indication.
                is the 3th octet of the destination address if two number params where provided.
        [octet] is the 4th octet of the destination address if first two params provided are numeric.
                is the username to use in the connection command if only two params where provided.
        [user]  is the username to use in the connection command. It must always be the last param.
    
    Examples:
        * **192.168 7** will connect to root@192.168.100.7

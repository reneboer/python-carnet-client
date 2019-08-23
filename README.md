# python-carnet-client
Python script we_connect_clinet.py emulates the VW WE Connect web site to send commands to your car and get status.

You must have a VW WE Connect (formerly CarNet) userid and password. Also make sure to logon to the portal https://www.portal.volkswagen-we.com first before using the script. The VW site prompts for several items at first logon the script does not handle.

This script requires the [requests](https://github.com/kennethreitz/requests) library. To install it, run `pip install requests`.

Based of work from wez3 at https://github.com/wez3/volkswagen-carnet-client
It has similar functions and Charging control for electric VW's

The first two parameters are your userid and password (in single quotes!), the optional third is the command.

Avaible commands to the script are:
  startCharge, stopCharge, getCharge, startClimat, stopClimat, getClimat, startClimate, getClimate, stopClimate, startWindowMelt, stopWindowMelt, getWindowMelt

If no command is specified the full car status is retreived.

Command example:
```
python we_connect_client.py '<userid>' '<pwd>' startCharge
```



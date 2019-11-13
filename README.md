# python-carnet-client
FYI. I have no time or options to develop this code further. A newer version can be found at https://github.com/bgewehr/volkswagen-carnet-client. Have fun developing this to the next level.

Python script we_connect_clinet.py emulates the VW WE Connect web site to send commands to your car and get status.

You must have a VW WE Connect (formerly CarNet) userid and password. Also make sure to logon to the portal https://www.portal.volkswagen-we.com first before using the script. The VW site prompts for several items at first logon the script does not handle.

As of version 2.6 the script supports Secure PIN based commands as well.

This script requires the [requests](https://github.com/kennethreitz/requests) library. To install it, run `pip install requests`.

Based of work from wez3 at https://github.com/wez3/volkswagen-carnet-client
It has similar functions and Charging control for electric VW's

The first two parameters are your userid and password (in single quotes!), the optional third is the command.

Avaible commands to the script are:
  startCharge, stopCharge, getCharge, startClimat, stopClimat, getClimat, startClimate, getClimate, stopClimate, startWindowMelt, stopWindowMelt, getWindowMelt, getLatestReport, getAlerts, getGeofences
Commands needing a secure pin  
  remoteUnlock, startRemoteVentilation, stopRemoteVentilation, startRemoteHeating, stopRemoteHeating

If no command is specified the full car status is retreived.

Usage:
```
usage: we_connect_client.py [-h] -u USER -p PASSWORD [-v VIN]
                            [-c {startCharge,stopCharge,getCharge,startClimate,stopClimate,getClimate,startWindowMelt,stopWindowMelt,getWindowMelt,getVIN,remoteLock,remoteUnlock,startRemoteVentilation,stopRemoteVentilation,startRemoteHeating,stopRemoteHeating,getRemoteHeating,getLatestReport,getAlerts,getGeofences}]
                            [-s SPIN] [-i {0,1,2,3,4,5,6,7,8,9}] [-d]

Control your Connected VW.

optional arguments:
  -h, --help            show this help message and exit
  -u USER, --user USER  Your WE-Connect user id.
  -p PASSWORD, --password PASSWORD
                        Your WE-Connect password.
  -v VIN, --vin VIN     Your car VIN if more cars on account.
  -c {startCharge,stopCharge,getCharge,startClimate,stopClimate,getClimate,startWindowMelt,stopWindowMelt,getWindowMelt,getVIN,remoteLock,remoteUnlock,startRemoteVentilation,stopRemoteVentilation,startRemoteHeating,stopRemoteHeating,getRemoteHeating,getLatestReport,getAlerts,getGeofences}, --command {startCharge,stopCharge,getCharge,startClimate,stopClimate,getClimate,startWindowMelt,stopWindowMelt,getWindowMelt,getVIN,remoteLock,remoteUnlock,startRemoteVentilation,stopRemoteVentilation,startRemoteHeating,stopRemoteHeating,getRemoteHeating,getLatestReport,getAlerts,getGeofences}
                        Command to send.
  -s SPIN, --spin SPIN  Your WE-Connect s-pin needed for some commands.
  -i {0,1,2,3,4,5,6,7,8,9}, --index {0,1,2,3,4,5,6,7,8,9}
                        To get the VIN for the N-th car.
  -d, --debug           Show debug commands.

```

Command example:
```
python we_connect_client.py -u '<userid>' -p '<pwd>' -c startCharge
```



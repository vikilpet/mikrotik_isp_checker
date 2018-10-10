# Mikrotik ISP checker script
Check ISP connection with multiple ping targets and advanced logic in multiple ISP setup.

### Features
- Any amount of ping targets
- SIP and L2TP connections removal
- Detection of quick interface reconnection
- Protection from launching another instance of script

### Prerequisites
WAN interfaces should be PPPoE or another stateful kind of interface.

RouterOS version > 6.37

### Installing
You **can't** just copy and paste that script. You shall edit it for your specific case. Things to change outside *SETTINGS* area:
- Change pppoe to your interface type (works only with stateful interfaces)
- Change actions that should be taken when interface changes it's status.

Save as script and run it from scheduler.
Different script with different name for each ISP.

#### \*\*\*
Feel free to ask questions or correct my spelling.
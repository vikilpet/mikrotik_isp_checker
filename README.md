# Mikrotik ISP Checker Script
Check ISP connection with multiple ping targets and advanced logic in multiple ISP setup.

### Features
- Any amount of ping targets
- SIP and L2TP connections removal
- Detection of quick interface reconnection
- Protection from launching another instance of script

### Prerequisites
ISP interfaces should be pppoe-client or another stateful kind of interface.

RouterOS version > 6.37

### Explanation
We should not trust only one host so we ping many.

We should remove SIP connections because of limitations of UDP + NAT schema. See this [great post](https://forum.mikrotik.com/viewtopic.php?t=129048#p641539) on official forum.

I use L2TP tunnels so I should remove their connections too because sometimes some of them had stopped working after problem with ISP interface.

Quick reconnection may happen between script launches. We can detect it with *uptime* property of pppoe interface and take respective actions.

### Installing
You **can't** just copy and paste that script. You shall edit it for your specific case. Things to change outside *SETTINGS* area:
- Change pppoe-client to your interface type (works only with stateful interfaces). If your interfaces not that kind then you should modify a lot to remove state-related (*monitor*, *uptime* and so on) things.
- Change actions that should be taken when interface changes status. My main action is changing of mangle rules state. You probably should just disable corresponding route.

One script for one ISP. If you have 3 ISP you should make 3 scripts.

#### \*\*\*
Feel free to ask questions or correct my spelling mistakes.
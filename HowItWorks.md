# Transitions #
The Location Changer works on transitions between locations. Two 'transitions' occur when you switch a location with your Mac: you leave a location and you go to another location. The key with this is that you can define transitions that occur when you leave a location regardless of where you are going (you can use a wild card to match any location) and define a transition between two specific locations or any location.

Transitions occur based on the following rules:
  * Fully wild carded locations (e.g. `*` to `*`) occur
  * Wild carded destinations for the given location then occur (e.g. from Work to any location)
  * Wild carded origins for the destination then occur (e.g. `*` to Work)
  * Fully specified locations occur (e.g. Work to Home)

Transitions are defined on a global scope (/etc/locationtab) or per user (~/.locationtab). Global actions run as root, whilst user actions run as that user.


# Actions #
The last part are the actions which define what to do when you transition from locations. These can be any script or executable that can be run on your system, for example a bash script or a compiled executeable. These actions are similar to the system used by cron, so you can also specify params.
# SargeAI-Genesys

This is the stock 1.5.2 SargeAI Framework that you can still download. Right out of the box it does "function" in Epoch 1.0.6.1 but with an extreme amount of errors.
I have already modified this version to eliminate most errors, however, most of the Urban Patrol Script is broken. Here is where we begin to demolish the myth that Sarge is dead!

line 20 sched_corpses.sqf

line 4 shed_safetyVehicle.sqf
if (vehicle _x != _x && !(vehicle _x in dayz_serverObjectMonitor) && !((typeOf vehicle _x) in DZE_safeVehicle) && (vehicle _x getVariable ["Sar_protect",0] != 1)) then {

Theres no reason to ever use ""Sarge"" as a variable ever, i have not seen any unit or object or vehicle initalized with this new unique var.

Going to test these theories and see if those applied changes indeed keep corpses and vehicles

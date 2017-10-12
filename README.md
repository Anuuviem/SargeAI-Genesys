# SargeAI-Genesys

This is the stock 1.5.2 SargeAI Framework that you can still download. Right out of the box it does "function" in Epoch 1.0.6.1 but with an extreme amount of errors.
I have already modified this version to eliminate most errors, however, most of the Urban Patrol Script is broken. Here is where we begin to demolish the myth that Sarge is dead!

///////Not This spot!!!
line 20 sched_corpses.sqf
if ((count units _group == 0) && !(_x getVariable["SAR_protect",false])) then {
\\\\\\\\\\\\\\\\\\

line 45 schec_corpses.sqf
if ((_x getVariable["bodyName",""] != "") && !(_x getVariable ["SAR_protect",false])) then {

line 4 shed_safetyVehicle.sqf
if (vehicle _x != _x && !(vehicle _x in dayz_serverObjectMonitor) && !((typeOf vehicle _x) in DZE_safeVehicle) && (vehicle _x getVariable ["Sarge",0] != 1)) then {

Going to test these theories and see if those applied changes indeed keep corpses and vehicles

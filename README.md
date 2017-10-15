# SargeAI-Genesys

This is the stock 1.5.2 SargeAI Framework that you can still download. Right out of the box it does "function" in Epoch 1.0.6.1 but with an extreme amount of errors.
I have already modified this version to eliminate most errors, however, most of the Urban Patrol Script is broken. Here is where we begin to demolish the myth that Sarge is dead!

<<<<<<< HEAD
for install...

in init.sqf 

within the (isServer) block, underneath the execVM "\z\addons\dayz_server\traders\chernarus11.sqf"; //Add trader agents 
add call compile preprocessfile "addons\SHK_pos\shk_pos_init.sqf";

at the bottom add
execVM "addons\UPSMON\scripts\Init_UPSMON.sqf";
[] execVM "addons\SARGE\SAR_AI_init.sqf";

in server.pbo\system\scheduler\sched_safetyVehicle.sqf line 4 add
&& (vehicle _x getVariable ["Sarge",0] != 1)
to
if (vehicle _x != _x && !(vehicle _x in dayz_serverObjectMonitor) && !((typeOf vehicle _x) in DZE_safeVehicle)) then {
so it looks like
if (vehicle _x != _x && !(vehicle _x in dayz_serverObjectMonitor) && !((typeOf vehicle _x) in DZE_safeVehicle) && (vehicle _x getVariable ["EAT_Veh",0] !=1) && (vehicle _x getVariable ["Sarge",0] != 1) && !((typeOf vehicle _x) in DZE_safeStatic)) then {

in server.pbo\system\scheduler\sched_corpses.sqf line 45 add
&& !(_x getVariable ["SAR_protect",false])
to
if (_x getVariable["bodyName",""] != "") then {
so it looks like
if ((_x getVariable["bodyName",""] != "") && !(_x getVariable ["SAR_protect",false])) then {

this is nearly fully working. Ive had very limited number of errors to include

Error in expression <c getVariable ["UPSMON_grpid","0"]);
if(_grpid==0) then{
KRON_UPS_Instances = KR>
 1:01:48   Error position: <_grpid==0) then{
KRON_UPS_Instances = KR>
 1:01:48   Error Undefined variable in expression: _grpid
 1:01:48 File mpmissions\DayZ_Epoch_11.Chernarus\addons\UPSMON\scripts\upsmon.sqf, line 184

 1:01:49 "Leader is still alive: SAR_leader_14"
 1:01:50 "Assigned new leader: <NULL-object>"
Error in expression <R_AI_debug;
};


_npc setVehicleVarname _leadername; 
_npc setVariable ["SAR_lea>
 1:01:50   Error position: <_leadername; 
_npc setVariable ["SAR_lea>
 1:01:50   Error Undefined variable in expression: _leadername
 1:01:50 File mpmissions\DayZ_Epoch_11.Chernarus\addons\UPSMON\scripts\UPSMON\common\MON_functions.sqf, line 2071
 
Error in expression <,2] call MON_nearestSoldiers;
if (count _vehicles>0) then {
_npc = [_vehicles se>
 1:01:54   Error position: <_vehicles>0) then {
_npc = [_vehicles se>
 1:01:54   Error Undefined variable in expression: _vehicles
 1:01:54 File mpmissions\DayZ_Epoch_11.Chernarus\addons\UPSMON\scripts\upsmon.sqf, line 298
=======
///////Not This spot!!!
line 20 sched_corpses.sqf
if ((count units _group == 0) && !(_x getVariable["SAR_protect",false])) then {
\\\\\\\\\\\\\\\\\\

line 45 schec_corpses.sqf
if ((_x getVariable["bodyName",""] != "") && !(_x getVariable ["SAR_protect",false])) then {

line 4 shed_safetyVehicle.sqf
if (vehicle _x != _x && !(vehicle _x in dayz_serverObjectMonitor) && !((typeOf vehicle _x) in DZE_safeVehicle) && (vehicle _x getVariable ["Sarge",0] != 1)) then {

Going to test these theories and see if those applied changes indeed keep corpses and vehicles
>>>>>>> 4c6839cb6d87bf04c251b15089eab3a3bf0913db

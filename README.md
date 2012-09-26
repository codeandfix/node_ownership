node_ownership
==============

Node Ownership (node_ownership)




# Prerequisites
########################

	1. reserve Playername "Sandbox" and protect it with a password.



# Configuration (requires restart)
########################

	1. Change ServerAdmin name in settings.lua if you want [optional]



# Installation
########################

	1. put init.lua and settings.lua into /minetest/games/minetest_game/mods/node_ownership/
	2. restart server



# Usage
########################

	NOTE:	If you use a command which needs <PlayerName> as Parameter, the Player you address needs to be online at the moment. Otherwise the command wont work.
		This does not apply to the Player named "Sandbox".


	Set Owner:
		As a Player with the "privs" privilege you (Grantor) can use this command to grant a concession to a Player (Concessionaire).
		Remember: Every Owner (Concessionaire) has the right to grant subconcessions for his concessionary area using Add Owner.

		Syntax:		/set_owner <PlayerName> <pos1.x>,<pos1.y>,<pos1.z> <pos2.x>,<pos2.y>,<pos2.z>
		
		Parameters:	<PlayerName> 		= Player's Name (Concessionaire)
				<pos1.x>..<pos2.z>	= Position of two points in the world describing a cuboid

		Example:	/set_owner JohnDoe -100,-100,-100 100,100,100


	Add Owner:
		As a Player with a granted concession (Concessionaire), you can give out subconcessions to other Players (Subconcessionaires).
		
		Syntax:		/add_owner <PlayerName> <pos1.x>,<pos1.y>,<pos1.z> <pos2.x>,<pos2.y>,<pos2.z>
		
		Parameters:	<PlayerName>		= Player's Name (Subconcessionaire)
				<pos1.x>..<pos2.z>	= Position of two points in the cuboid of the concession describing a smaller or equal cuboid (unstrict subset)

		Example:	/add_owner SamDoe -100,-100,-100 100,100,100


	List Areas:
		As a Player with the "privs" privilege (Grantor) you can list all areas describing all current concessions and subconcessions.
		As a Player with a concession (Concessionaire) you can list only your areas.

		The Area Number which is shown is required to delete a concession.
		For each tuple of (cuboid,playername) there is one area identifier.

		Syntax:		/list_areas


	Remove Areas:
		To remove a concession belonging to a Player (Concessionaire/Subconcessionaire) you need the AreaID from the List Areas command.

		Syntax:		/remove_areas <areaID>

		Parameters:	<areaID>		= Area Identifier from the List Areas command.

		Example:	/remove_areas 1


	Change Area Owner:
		To change a Players (Concessionaire) concession you can use the Change Area Owner command.
		You need the AreaID from List Areas and the Playername of the new concessionaire.

		Syntax:		/change_area_owner <areaID> <PlayerName>

		Parameters:	<areaID>		= Area Identifier from the List Areas command.
				<PlayerName>		= Player's Name of the new Concessionaire

		Example:	/change_area_owner 1 FooDoe


	Sandbox Concession:
		A Sandbox concession is a concession where everyone with interact privilege can dig or place.

		To grant a Sandbox concession you have to set an owner to the Player named "Sandbox".
		It also works for subconcessions using add owner.



# License and Authors
########################

	see: http://minetest.net/forum/viewtopic.php?id=846




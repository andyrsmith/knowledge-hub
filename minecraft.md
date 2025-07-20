# Minecraft

## Setup Minecraft Bedrock Server

1. Download Minecraft Bedrock Server and [https://www.minecraft.net/en-us/download/server/bedrock](https://www.minecraft.net/en-us/download/server/bedrock)
    Unzip contents to Server
2. Download desired addon from CurseForge or other sites. Ex [Better on Bedrock](https://www.curseforge.com/minecraft-bedrock/addons/better-on-bedrock)
3. Unzip pack and look for a manifest.json in both resources and behaviors folder
4. Copy the uuid and version line from each file.
5. Upload the behaviors folder within the behaviors folder of server, and rename the folder that you just uploaded to something similar to the pack you just uploaded like betterMC
6. Repeat a similar process for resources.
7. Within your worlds folder create a world_behavior_packs.json. This would be the folder that is worlds/<your world name>.  Put your pack uuid and version like the following.
```
[
	
	{
		"pack_id" : "40d18d86-f454-4361-bbcf-b118274dec17", //Packs Resource UUID
		"version" : [ 1, 0, 1 ]  ///Packs Version
	}
]
```
8. Repeat the same for resources except file will be world_resource_packs.json
```
[
	
	{
		"pack_id" : "e0992d5f-e7d3-4260-abba-2da0d6015c05", //packs Resource UUID
		"version" : [ 1, 0, 1 ]
	}
]
```
9.  Start the server with command LD_LIBARY=. ./bedrock_server
10. Go to client devices start device and create a new server connection in the server tab. Once it launches it should download the pack onto your device and you should see the Packs logo as it is loading.  Better the Bedrock has it's own logo, not sure about other packs.

## Upgrading Bedrock Server

Steps in Upgrading Bedrock server

1. Unzip bedrock server to new folder
2. Stop server
3. copy worlds to new bedrock directory
4. copy resource/betterMC to new bedrock
5. copy behavior/betterMC to new bedrcok
6. Start server in new directory

## Good minecraft Bedrock Seeds

https://screenrant.com/minecraft-best-seeds-bedrock-edition/

-223684598022597855
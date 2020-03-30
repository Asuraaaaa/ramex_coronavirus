# ramex_coronavirus
Script pour FiveM-France -> https://fivem-france.net/

Ressources Requise : 
InteractSound : https://github.com/plunkettscott/interact-sound

AntiVirus Possible en créant un item AntiDote exemple :

player, distance = GetClosestPlayer()
		if(distance ~= -1 and distance < 2) then
		        TaskStartScenarioInPlace(GetPlayerPed(-1), 'CODE_HUMAN_MEDIC_TEND_TO_DEAD', 0, true)
                Citizen.Wait(8000)
                ClearPedTasks(GetPlayerPed(-1));
		        TriggerServerEvent('delete:corona', GetPlayerServerId(player))
	    else
		    TriggerEvent("es_freeroam:notify", "CHAR_CALL911", 1, "Antidote", false, "Pas de joueur proche, rapprocher vous du joueur pour lui injecter")
		    TriggerEvent("player:receiveItem", 115, 1)
		end


# Stalker-Anomaly-Brotherhood

Thank you for visiting my mod project. For the moment it's still in the early phase of developpment.

Special thanks to the Anomaly discord community which helped me throughout this project, especially

- xcvb for always helping out and providing some scripts used in this mod
- NLTP-Ashes for sharing his huge knowledge
- Ghentuong for being an inspiration and a reference, and providing some scripts used in this mod
- Ravenascendant for helping out if I had a question
- igigog for helping out if I had a question
- demonized for helping out if I had a question



Version 0.1a

Compatibility:

    DLTX adaptation will follow in the endphase

- For the moment I recommend playing this mod without any other mods - at least none which would be in conflict. If you really want to use other mods, use this guide to make your own monkey patch.

- If you want to use other mods which use these three files, you have to include my mod too. You can do this by opening the concerned file with notepad++ and adding the required lines

        - configs > creatures > spawn_section.ltx
            #include "spawn_sections_brotherhood.ltx"

        - configs > creatures > monsters.ltx
            #include "m_z_legendary.ltx"
        - configs > system.ltx

                    - [dialogs]   dialogs_brotherhood, dialogs_brotherhood_fa, dialogs_brotherhood_ms
                    - [profiles]  npc_profile_brotherhood
                                  character_desc_brotherhood
                                  
- If the other mod also uses the following files, it becomes more problematic and you will need to find my added code lines and paste them into the other file (you can find it by comparing the two files in notepad++ and adding mine):                                  
                                  
        - configs > gameplay > character_desc_[base mod].xml

                I added some dialogues to existing characters, of course they have to be added if the files are overwritten (list might follow)

        - configs > items > trade >
                       - overwriting these files can have a potential problems with some quests: - trade_hawaiian.ltx
                       - the Quest is not made yet - so for now you can ignore trade files

       -  configs > scripts >

                    - obviously very problematic, will have to make a whole list or learn DLTX. I strongly recommend not using any mods which would tamper with these files.

                    

      -  gamedata > scripts > actor_effects.script 
                    
            - I disabled the create stash animation for the backpack for a quest (by adding --): 
            
                  - line 1747 to 1749 : --elseif (id == ruck_last_backpack) then 
                                        --ruck_last_backpack = -1 
                                        --play_anm = true

            - this means, if a mod also modified actor_effects and is loaded after my mod - you might get problems (or not - tell me)
            - you can monkey patch this by diasbling these three lines in the other mod

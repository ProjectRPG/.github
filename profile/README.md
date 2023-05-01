# Project RPG
allows you to fully customize an RPG experience within minecraft.  You simply add the mods with the features you want alongside Project RPG and they will seamlessly integrate to give you the exact RPG experience you desire.

[Addon Makers Wiki]()
<hr>

## Feature Options
RPGs all have common elements which make them RPGs.  Project RPG breaks these down into various systems that addons customize.  Depending on the type of RPG content you want to modify, select an addon that customizes that system.

|System|System Definition|Exclusivity|Links|
|:---|:---|:---:|:---:|
|Progression|How players advance during play.  In many RPGs, this is through an "experience" system.|Only one system can be present|[CurseForge]() [Modrinth]()|
|Progression Addons|Addons to the addons, these systems give the progression system extra information that can be used for things like bonuses to xp.|Many can be added|[CurseForge]() [Modrinth]()|
|Gating|"Gating" is the system of putting barriers in the way of features.  For example, not being skilled enough to use an item or travel to an area.  Gating systems are broken down into four sub-types which you can read about [HERE](#gating-types)| Many can be added|[CurseForge]() [Modrinth]()|
|Events|When specific things happen in a game, we call them "events".  breaking a block, blocking a mob attack with a shield, and taking fall damage are all examples of events|Many can be added|[CurseForge]() [Modrinth]()|
|Abilities|Special behavior that players unlock and use as they play.  These can be passive abilities like stat boosts, or active ones like spells|Many can be added|[CurseForge]() [Modrinth]()|
|Ability System|Any mod can add abilities, but how the player accesses them is governed by this system.  Examples of systems might be a skill tree or simply abilities that unlock automatically at certain skill levels|Only one system can be present|[CurseForge]() [Modrinth]()|
|Parties|Most RPGs have some way for players to band together.  This system governs how that banding works.|Only one system can be present|[CurseForge]() [Modrinth]()|
|Party Addons|WIP|Many can be added|[CurseForge]() [Modrinth]()|
|Features|Extra functionality that interacts with the above systems but isn't exclusive to RPGs as a whole|Many can be added|[CurseForge]() [Modrinth]()|
<hr>

## One Single Configuration System
Project RPG also makes it easy to mix and match your addons by making your configuration files dynamic.  Project RPG uses datapacks to configure your world (Check out our [Datapack Builder](projectrpg.github.io)).

To make your configurations dynamic, Project RPG lets you include configs for non-present addons so that they are there if the addon is used and ignored if absent.
```json5
"progression": [
    //gets used because the addon is present
    {"type":"example:present", "setting":"value"}, 
    //gets ignored because the addon isn't.  However, if the 
    //user swapped these addons, they would have a configuration already
    {"type":"absent:example", "configuration":0}
]
```
<hr>

## A Shared User Interface
Project RPG also provides a unified interface for all addons to make interacting with these features in-game as seamless as possible.  

(images, WIP)
<hr>

## Gating Types
You are dedicated to have read this far.  Gating is broken down into four types.  In all cases, the gating system is given the same information as the system it gate keeps for and uses this to decide if that system is allowed to perform its function.
|Type|Purpose|
|:---|:---|
|Progression|Determines if a user is permitted to gain progress in this situation|
|Ability|Determines if an ability can activate.  This is in addition to any restrictions imposed by the ability system itself|
|Event|Determines if an event should be cancelled or not.  Doing so prevents all other systems and gate checks from being executed|
|Feature|Determines if a feature can execute in this situation|
|||

When choosing gating addons, keep in mind which gating types they affect as well as how they determine when to block features to help you determine if a gating system is right for you.




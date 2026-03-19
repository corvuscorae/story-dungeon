Story Dungeon

Story Dungeon is a procedural dungeon generator built in Lua that combines algorithmic map generation with dynamic narrative creation. 
The system generates unique dungeon layouts, populates them with story-driven room descriptions, and tracks player progression through 
objectives and exploration.

Features

Procedural Dungeon Generation

-Uses Binary Space Partitioning (BSP) to generate dungeon layouts
-Recursively splits the map into a node tree structure based on depth
-Creates interconnected rooms and hallways from the generated tree
-Dungeon is created through a random seed based one time

Dynamic Story Generation

-Integrates a story system that builds narratives tied to the dungeon layout
-Each room is assigned objectives and contextual story elements
-Story content adapts to the generated structure of the dungeon

Grammar-Based Room Descriptions

-Room descriptions are generated using a custom grammar system
-Produces varied and reusable paragraph-style descriptions
-Enhances immersion by making each room feel distinct


Player State Tracking

-Randomly places the player in a generated room at the start
-Tracks:
    Visited rooms
    Active objectives
    Completed objectives
-Supports progression-based gameplay within the generated dungeon


Project Structure

story-dungeon/
│
├──conf.lua
├──descriptionGenerator.lua
├──entity.lua
├──main.lua
├──story_handler.lua
├──text.lua
├──wall.lua

conf.lua
-confgures function for the Love2D game engine

descriptionGenerator.lua
-generates descriptive text for each room using a grammar system
-text is based on room size

entity.lua
-creates solid entities for map

main.lua
-creates a BSP tree by recursively splitting the map
-leaf nodes become rooms
-connection between nodes form hallways
-handles all player movement logic and placement
-tracks player progress of objectives and rooms visited

story_handler.lua
-sorts and returns objectives for the player to accomplish.
-if objectives are considered short in one room, combines them into one objective and returns updated objective list

tex.lua
-library of objectives and story telling

wall.lua
-creates wall instances for the map


Technologies Used
-Lua
-Procedural genration algorithms (BSP)
-Grammar-based text generation
-Love 2D engine


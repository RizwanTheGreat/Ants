# Ants
Ant Farm Simulation
Overview
Ant Farm Simulation is a C++ console application that models the behavior of ant farms within a simulated environment. Players can create ant farms, spawn ants of different types, distribute resources, and observe their interactions over time. The simulation is dynamic, allowing multiple commands to modify and monitor the state of the ant farms.

Features
Dynamic Ant Farms: Spawn ant farms with specific coordinates and species.

Ant Types: Create and manage different types of ants, including Workers, Warriors, and Queens.

Resource Management: Allocate resources such as food to specific ant farms.

Simulation Ticks: Observe the behavior of ants over a specified number of simulation ticks.

Farm Summary: Get detailed reports about each ant farm, including the ants’ kills and activities.

Installation
Clone the repository:

bash
git clone https://github.com/yourusername/ant-farm-simulation.git
Navigate to the project directory:

bash
cd ant-farm-simulation
Compile the program:

bash
g++ -o ant_farm_simulation ant_farm_simulation.cpp
Run the program:

bash
./ant_farm_simulation
How to Use
Commands
Spawn a new ant farm:

spawn <x> <y> <species>
Example:

spawn 10 20 Worker
Creates a new ant farm at coordinates (10, 20) with the Worker species.

Give resources to an ant farm:

give <farmId> <resource> <amount>
Example:

give 1 food 50
Allocates 50 units of food to the ant farm with ID 1.

Perform simulation ticks:

tick [<ticks>]
Example:

tick 5
Executes 5 simulation ticks. If no number is specified, the default is 1 tick.

View farm summary:

summary <farmId>
Example:

summary 1
Displays details about the ants and resources in the ant farm with ID 1.

Exit the simulation:

exit
Terminates the program.

Example Session
plaintext
> spawn 10 20 Worker
Ant farm spawned at (10, 20) with species: Worker.
> give 1 food 50
Food added to farm 1. Total food: 50
> tick 3
Performed 3 tick(s).
> summary 1
Ant Farm Summary (Farm 1):
Worker - Kills: 0
> exit
Code Structure
Classes
Meadow (Singleton)

Manages all ant farms.

Provides methods for creating farms, allocating resources, ticking simulation, and generating summaries.

AntFarm

Represents an individual ant farm.

Contains ants and resources.

Handles resource management and ant actions.

Ant (Base Class)

Abstract class representing a generic ant.

Defines core ant properties and actions.

Ant Subclasses

WorkerAnt: Responsible for foraging.

WarriorAnt: Specializes in hunting.

QueenAnt: Spawns eggs.

AntRoom

Factory pattern for creating ants.

WorkerRoom

Specific implementation of AntRoom for creating different ant types.

Main Flow
The commandLineInterface function handles user input and delegates actions to the appropriate Meadow or AntFarm methods.

The Meadow class coordinates global operations across all farms.

Future Enhancements
Add more resource types (e.g., water, shelter).

Introduce ant interactions, like battles or cooperative behaviors.

Implement a graphical user interface (GUI).

License
This project is licensed under the MIT License. See the LICENSE file for details.

# Mars-Exploration-Project
Project Based on OOP and Data Structure in C++.There are number of missions of different types need to be assigned to rovers in order  to be performed


This project is perfect practice on OOP and Data Structure using C++ language

Missions: There is a number of missions of different types (Emergency, mountainous and polar missions.

● Emergency missions must be assigned first before mountainous and polar missions.
● Mountainous missions are missions to mountainous regions of Mars and must be conducted by rovers equipped to navigate in such regions.
● Polar missions are missions to the polar ice caps of Mars and must be conducted by rovers equipped to navigate in such regions.

Each Mission has a Destination and Duration

-------------------------------------------------------------------------------------------------------------------------------------------------------------Rovers: There are 3 types of rovers
● Emergency rovers are rovers that are over-equipped and ready for emergency missions in almost any region.
● Mountainous rovers are rovers that can navigate in mountainous regions.
● Polar rovers are rovers that can navigate in polar regions.

Each Rover has -Checkup Duration: the rover needs to perform after completing N missions.
-Speed

----------------------------------------------------------------------------------------------------------------------------------------------------------
Assigning Missions to available rovers criteria:
● First, emergency missions are assigned to ANY available rover of any type. But with higher priority to emergency rovers than mountainous rovers and the last choice is the polar rovers.
● Second, polar missions are assigned using the available polar rovers only.
● Third, mountainous missions are assigned using any type of rover except polar rovers. Where mountainous rovers have higher priority than emergency rovers.
● Polar and mountainous missions are assigned based on first-come-first-served.
● Emergency missions, are assigned based on the priority queue.With priority equation
                                  Priority=(SignificanceTarget_LoactionMission_Duration)/Formulation_Day;

Promotion feature:
● For mountainous missions if it is still waiting unassigned, a request can be issued(from the input file) to promote the mission to become an emergency one. ● For mountainous missions, if a mission waits more than AutoP days from its formulation day to be assigned to a rover, it is automatically promoted to be an emergency mission.(AutoP is read from the input file)

Cancellation feature:
● For mountainous missions if it is still waiting unassigned, a request for mission cancellation can be issued (from the input file).

-----------------------------------------------------------------------------------------------------------------------------------------------------------
For Demo to test our system just follow the format of the input file(Test.txt)

Example:
2 ➔mode
3 3 2 ➔ no. of rovers of each type
1 2 2 ➔ rover speeds of each type (km/h)
3 9 8 7 ➔ no. of missions before checkup and the checkup durations
25 ➔ auto promotion limit
8 ➔ no. of events in this file
F M 2 1 100 4 5 ➔ formulation event example
F M 5 2 250 4 4
F E 5 3 500 6 3
F P 6 4 900 7 4
X 10 1 ➔ cancellation event example
F M 18 5 560 5 9
P 19 2 ➔ promotion event example
F P 25 6 190 3 1

The sequence of Data of Events:

❑The formulation event line has the following information:
▪ F (letter F at the beginning of the sentence) means a mission formulation event.
▪ TYP is the mission type (M: mountainous, P: polar, E: emergency).
▪ ED is the event day.
▪ ID is a unique sequence number that identifies each mission.
▪ TLOC is the mission’s target location (in kilometers from the base station).
▪ MDUR is the number of days needed to fulfill the mission requirements at the target location.
▪ SIG is the mission’s significance.

❑ The cancellation event line has the following information:
▪ X (Letter X) means a mission cancellation event.
▪ ED is the event day.
▪ ID of the mountainous mission to be canceled.

❑ The promotion event line has the following information:
▪ P (Letter P) means a mission promotion event.
▪ ED is the event day.
▪ ID of the mountainous mission to be promoted to an emergency.

sample output:(Output. txt) 
CD ID FD WD ED ➔ Completion day ID formulation day Waiting period Execution day
18 1 7 5 6
44 10 24 2 18
49 4 12 20 17
………………………………………………
………………………………………………
Missions: 124 [M: 100, P: 15, E: 9]
Rovers: 9 [M: 5, P: 3, E: 1]
Avg Wait = 12.3, Avg Exec = 25.65
Auto-promoted: 20%

------------------------------------------------------------------------------------------------------------------------------------------------------------
Program Interface: 1. Interactive Mode: This allows the user to monitor the missions and rovers day by day by pressing enter to begin a new day.
      output keys:[] ➔ IDs of emergency missions or rovers.
                  () ➔ IDs of polar missions or rovers.
                  {} ➔ IDs of mountainous missions or rovers.
                  
2. Step-By-Step Mode: Automatic version of the interactive mode where a new day begins after 1 sec (for simulation purposes).
3. Silent Mode: the program produces only an output file shown above.

--------------------------------------------------------------------------------------------------------------------------------------------------------------The main loop of the program is in main.c

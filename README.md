# 24346_Gishunshu_TrafficLight_diagram

Overview
The Gishushu Traffic Light System consists of several states and transitions to control vehicle and pedestrian flow. The states include Red, Green, and Yellow lights for vehicles, as well as a Pedestrian Cross phase for pedestrians.

Specifications
States
1. Red Light
Purpose: Holds vehicle traffic to ensure safety and accommodates pedestrian crossings.
Sub-States:
Waiting: The default condition where the system waits for either a timer signal or a pedestrian input.
Pedestrian Cross: A nested state for safe pedestrian crossing.
Crossing: A sub-state within Pedestrian Cross that allows pedestrians to walk across safely.
2. Green Light
Purpose: Allows vehicle traffic to proceed through the intersection.
Sub-States:
Active: The primary state where the Green light is on, signaling vehicles to move.
Yellow: A transitional state alerting vehicles to prepare to stop.
Warning: A sub-state of Yellow that briefly alerts vehicles, preparing them for the upcoming Red light.
Transitions
Transition	Trigger Condition	Action
Red Light to Green Light	The Red timer expires, and no pedestrian crossing request is active.	The light changes to Green, allowing vehicles to proceed.
Green Light to Yellow Light	The Green timer expires.	The system transitions to Yellow, warning drivers to prepare to stop.
Yellow Light to Red Light	The Yellow timer expires.	Completes the caution phase, switching to Red to stop traffic and start a new cycle.
Red Light to Pedestrian Cross	Pedestrian button pressed while Red is in the Waiting state.	The system moves to Pedestrian Cross, allowing pedestrians to cross safely.
Pedestrian Cross to Red Light	Pedestrian crossing timer expires.	Ends the pedestrian crossing, returning to Red for the next vehicle or pedestrian flow.
Crossing within Pedestrian Cross	Pedestrian crossing timer expires within Crossing.	Returns from Crossing to Waiting under Red, preparing for the next transition.


Trigger Condition: The pedestrian crossing timer runs out.
Action: Ends the pedestrian crossing phase, returning to Red to reset the light for the next vehicle or pedestrian flow.
Crossing within Pedestrian Cross

Trigger Condition: The pedestrian crossing timer expires within the Crossing state.
Action: Returns from Crossing to Waiting under Red, allowing the system to reset and prepare for the next transition.

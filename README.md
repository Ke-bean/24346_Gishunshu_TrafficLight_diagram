# 24346_Gishunshu_TrafficLight_diagram

Specifications
States
Red Light

Objective: Holds vehicle traffic at a standstill to ensure safety and accommodate pedestrian crossings.
Sub-States:
Waiting: The initial or default condition of the Red light, where the system waits for either a timer signal or pedestrian input.
Pedestrian Cross: A special state nested within Red, activated when pedestrians need to cross the road safely.
Crossing: A sub-state where pedestrian crossing is active, allowing pedestrians to safely walk across.
Green Light

Objective: Grants permission for vehicle traffic to proceed through the intersection.
Sub-States:
Active: The primary state where the Green light is on, signaling vehicles to move.
Yellow: An intermediary state that serves as a transition, signaling vehicles to prepare to stop.
Warning: A sub-state of Yellow that briefly alerts vehicles to halt, preparing them for the upcoming Red light.
Transitions
Red Light to Green Light

Trigger Condition: The waiting period for Red expires, and there is no active pedestrian crossing request.
Action: The light changes to Green, allowing vehicles to proceed through the intersection.
Green Light to Yellow Light

Trigger Condition: The Green timer expires.
Action: The system transitions from Green (Active) to Yellow, warning drivers to prepare for a stop.
Yellow Light to Red Light

Trigger Condition: The Yellow timer expires.
Action: Completes the caution phase, switching from Yellow to Red to stop vehicle traffic and allow a new cycle to begin.
Red Light to Pedestrian Cross

Trigger Condition: The pedestrian button is activated while Red is in the Waiting state.
Action: The system moves from Red to Pedestrian Cross, enabling pedestrians to cross safely.
Pedestrian Cross to Red Light

Trigger Condition: The pedestrian crossing timer runs out.
Action: Ends the pedestrian crossing phase, returning to Red to reset the light for the next vehicle or pedestrian flow.
Crossing within Pedestrian Cross

Trigger Condition: The pedestrian crossing timer expires within the Crossing state.
Action: Returns from Crossing to Waiting under Red, allowing the system to reset and prepare for the next transition.

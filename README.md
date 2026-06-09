 Title
 
 Festival Gate Throughput and Overflow Management Simulator

Overview

The Festival Gate Throughput and Overflow Management Simulator is a JavaScript-based project that models how attendees enter a festival through multiple gates. Each gate has a limited processing capacity, and when the number of arriving attendees exceeds that capacity, the extra attendees are automatically rerouted to the next available gate.

The simulation runs across multiple time intervals (ticks) and provides a summary of how many attendees each gate successfully processes.

Features
Simulates attendee flow through multiple festival gates.
Processes attendees according to each gate's capacity.
Detects and handles overflow situations.
Automatically reroutes excess attendees to neighboring gates.
Tracks total attendees processed by each gate.
Generates a throughput summary after the simulation.
Supports multiple time blocks (e.g., Morning and Night).
Project Structure
Data Sets

The project contains two gate configurations:

Morning Gates – Represents attendee traffic during the morning period.
Night Gates – Represents attendee traffic during the night period.

Each gate contains:

{
  id: "North",
  capacity: 5,
  queue: [3, 6, 2, 4]
}
Property	Description
id	Gate identifier
capacity	Maximum attendees that can be processed per tick
queue	Array representing arriving attendees at each tick
Functions
initializeThroughput(gates)

Creates an object to track the total number of attendees processed by each gate.

Returns:

{
  North: 0,
  East: 0,
  South: 0,
  West: 0
}
processGateFlow(gate, tickIndex)

Processes attendees for a specific gate during a particular tick.

Returns:

{
  processed: number,
  overflow: number
}
rerouteOverflow(gates, currentGate, tickIndex, overflowAmount)

Transfers excess attendees to the next gate in the sequence.

Example:

2 attendees rerouted to East
handleGateAtTick(gates, gate, tickIndex, throughputSummary)

Handles all gate operations during a single tick:

Displays arriving attendees
Processes attendees
Updates throughput statistics
Reroutes overflow attendees
printSummary(summary)

Prints the total number of attendees processed by each gate.

Example:

Throughput Summary

North: 15 attendees processed
East: 12 attendees processed
South: 10 attendees processed
West: 8 attendees processed
simulateFestival(gates, timeBlock)

Runs the complete festival simulation.

Steps:

Initialize throughput tracking.
Loop through all ticks.
Process every gate during each tick.
Handle overflow rerouting.
Display final throughput summary.
How It Works
Attendees arrive at each gate according to the queue array.
Each gate processes attendees up to its capacity.
Remaining attendees become overflow.
Overflow attendees are redirected to the next gate.
The process repeats for every tick.
A final report shows total attendees processed per gate.
Example Output
Morning Simulation

Tick 1

Processing North...
3 attendees arriving.

Processing East...
2 attendees arriving.

Processing South...
1 attendees arriving.

Processing West...
4 attendees arriving.
Overflow of 2 attendees. Rerouting...
2 attendees rerouted to North

Throughput Summary

North: 14 attendees processed
East: 11 attendees processed
South: 7 attendees processed
West: 8 attendees processed
Technologies Used
JavaScript (ES6)
Arrays
Objects
Loops
Functions
Console Logging
Learning Objectives

This project demonstrates:

Simulation modeling
Queue management
Overflow handling
Data aggregation
Object manipulation
Loop control
Function decomposition
Real-world event traffic management concepts
Future Improvements
Dynamic gate opening and closing.
Priority attendee lanes.
Real-time visualization dashboard.
Multiple rerouting strategies.
Performance analytics and charts.
Randomized attendee arrivals.
Web-based user interface.
Author

Festival Gate Throughput and Overflow Management Simulator
A JavaScript project for learning queue processing, traffic flow simulation, and overflow management in event operations.

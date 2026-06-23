# Discrete-Event Simulation: Travel Agency Queuing System

Simulates a two-employee travel agency using discrete-event simulation (SimPy) to estimate queue lengths, utilization rates, and customer wait times.

## System Description

- Customers arrive with interarrival times uniformly distributed between 7 and 30 minutes
- **Employee 1** provides tour information (service time: U[5, 7] min); serves as a priority resource — walk-in customers are served first
- **Employee 2** handles financial/booking details (service time: U[4, 20] min)
- After E2, customers either complete a booking (70%) or return to E1 for a second consultation (30%; service time: U[3, 7] min)

## What the Simulation Tracks

- Number of customers at each resource over time (step-function plots)
- Time-averaged queue length at E1 and E2 (area-under-curve / total simulation time)
- Resource utilization rates

## Key Implementation

- Custom `MonitoredResource` class extending `simpy.Resource` to log queue-length changes with timestamps
- Priority queue at E1 (walk-ins take precedence over returning customers)
- All service and interarrival times generated from uniform distributions matching the problem specification

## Tech Stack
- Python 3
- `simpy` · `numpy` · `scipy` · `matplotlib`

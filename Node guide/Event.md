# Event Node

## Description
The Event node is a key component in the node system, serving as the entry point for workflows triggered by specific occurrences within the system. It allows for the creation of event-driven architectures, enabling responsive and dynamic behavior in your projects.

## Usage
1. Place the Event node at the beginning of your workflow.
2. Configure the event type and any necessary parameters.
3. Connect the `exec_out` output to the first action in your event-handling sequence.

## Connections
- Output:
    - `exec_out` (exec): The outgoing execution flow, triggered when the event occurs

## Related Nodes
- [OnRun](on-run-node.md): Triggered when the workflow is first run
- [OnTick](on-tick-node.md): Triggered at regular intervals
- [OnRedstone](on-redstone-node.md): Triggered by redstone signal changes
- [Conditional](conditional-node.md): Often used immediately after events to check conditions

## Example
Create a workflow that responds to a specific event:

1. Place an Event node (e.g., OnRedstone) at the start of your workflow.
2. Connect its `exec_out` to a [Conditional](conditional-node.md) node to check the event details.
3. Based on the condition, connect to different action sequences (e.g., [PlaySound](play-sound-node.md) for one case, [SpawnParticle](spawn-particle-node.md) for another).

This setup allows you to create complex, event-driven behaviors in your system.

## Note
The Event node is an abstract base for specific event types. In practice, you'll use specialized event nodes like OnRun, OnTick, or custom event nodes that extend this base node.
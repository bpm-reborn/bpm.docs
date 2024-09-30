# Action Node

## Description
The Action node is a foundational component in the node system, representing a single executable action within a workflow. It serves as a base for many other node types and provides a standardized way to handle execution flow.

## Usage
1. Connect the incoming execution flow to the `exec_in` input.
2. Implement the desired action logic within the node.
3. Continue the execution flow through the `exec_out` output.

## Connections
- Input:
    - `exec_in` (exec): The incoming execution flow
- Output:
    - `exec_out` (exec): The outgoing execution flow

## Related Nodes
- [Print](print-node.md): A simple action that prints a message
- [SetVariable](set-variable-node.md): An action that sets a variable value
- [PlaySound](play-sound-node.md): An action that plays a sound
- [SpawnParticle](spawn-particle-node.md): An action that spawns particles

## Example
While the Action node itself is abstract, it forms the basis for creating custom actions:

1. Create a new node that extends the Action node.
2. Implement the desired functionality within the new node.
3. Use the `exec_in` and `exec_out` connections to integrate it into your workflow.

For instance, you could create a custom "SendEmail" node that extends the Action node, implementing the email sending logic within the node while using the standard execution flow inputs and outputs.

## Note
The Action node is typically used as a base class for other nodes rather than being used directly in workflows. It provides a consistent interface for nodes that perform discrete actions within the system.
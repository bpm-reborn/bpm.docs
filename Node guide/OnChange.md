# OnChange Node

## Description
The OnChange node is a powerful tool for detecting changes in values within your workflow. It triggers an execution flow only when the input value differs from its previous state, making it ideal for event-driven systems and optimizing performance by reducing unnecessary operations.

## Usage
1. Connect the value you want to monitor to the `value` input.
2. Link the desired action to the `exec_out` output.
3. The node will execute the output flow only when the input value changes.

## Connections
- Input:
    - `exec_in` (exec): The incoming execution flow
    - `value` (any): The value to monitor for changes
- Output:
    - `exec_out` (exec): Executed when the value changes

## Related Nodes
- [GetVariable](get-variable-node.md): Retrieve a variable to monitor
- [Print](print-node.md): Output the changed value
- [SetVariable](set-variable-node.md): Update a variable when a change is detected
- [Conditional](conditional-node.md): Perform different actions based on the new value

## Example
Use the OnChange node to trigger actions when a sensor reading changes:

1. Connect a sensor output (e.g., from a [Proxy](proxy-node.md) node) to the `value` input.
2. Link a [Notification](notification-node.md) to the `exec_out` to alert when the sensor value changes.
3. Optionally, use a [SetVariable](set-variable-node.md) node to store the new value for later use.

This setup will notify you of sensor changes without constantly sending redundant alerts.
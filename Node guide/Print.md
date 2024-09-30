# Print Node

## Description
The Print node is a simple yet essential tool for debugging and monitoring your workflow. It outputs a message to the console, allowing you to track the execution flow and display variable values during runtime.

## Usage
1. Connect the execution flow to the `exec_in` input.
2. Provide the message to be printed to the `value` input.
3. The node will print the message to the console and continue the execution flow.

## Connections
- Input:
    - `exec_in` (exec): The incoming execution flow
    - `value` (string): The message to print
- Output:
    - `exec_out` (exec): The continuing execution flow

## Related Nodes
- [ToString](to-string-node.md): Convert non-string values for printing
- [Concatenate](concatenate-node.md): Combine multiple strings for a complex message
- [GetVariable](get-variable-node.md): Retrieve a variable value for printing
- [OnChange](on-change-node.md): Print when a value changes

## Example
Use the Print node to debug your workflow:

1. Place a Print node after a complex operation.
2. Connect the operation's output to the `value` input of the Print node.
3. Run your workflow and check the console for the printed values.

This setup allows you to verify that your operations are producing the expected results at various stages of your workflow.

## Note
While useful for debugging, remember to remove or disable Print nodes in production environments to avoid cluttering the console with unnecessary output.
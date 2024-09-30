# Conditional Node

## Description
The Conditional node is a fundamental control flow component in the node system. It allows for branching logic based on a boolean condition, enabling the creation of dynamic and responsive workflows.

## Usage
1. Connect a boolean value to the `condition` input.
2. Link the desired execution paths to the `true` and `false` outputs.
3. The node will execute the appropriate path based on the condition's value.

## Connections
- Input:
    - `condition` (boolean): The condition to evaluate
    - `exec_in` (exec): The incoming execution flow
- Output:
    - `true` (exec): Executed if the condition is true
    - `false` (exec): Executed if the condition is false

## Related Nodes
- [Boolean](boolean-node.md): Can be used to provide a static boolean value
- [And](and-node.md): Combine multiple conditions
- [Or](or-node.md): Combine multiple conditions
- [EqualTo](equal-to-node.md): Compare values for equality
- [GreaterThan](greater-than-node.md): Compare numerical values
- [LessThan](less-than-node.md): Compare numerical values

## Example
Use the Conditional node to create an if-else structure in your workflow:

1. Connect a [GetVariable](get-variable-node.md) node to the `condition` input.
2. Link a [Print](print-node.md) node to the `true` output for the "if" case.
3. Link another [Print](print-node.md) node to the `false` output for the "else" case.

This setup will print different messages based on the variable's value.
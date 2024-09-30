# Literal Node

## Description
The Literal node represents a constant value in the node system. It's used to input fixed data into your workflows, providing a way to use hard-coded values alongside dynamic ones.

## Usage
1. Place the Literal node in your workflow where a constant value is needed.
2. Set the desired value in the node's properties.
3. Connect the node's output to other nodes that require this constant input.

## Connections
- Output:
    - Value output (type varies): The constant value set in the node

## Related Nodes
- [Int](int-node.md): For integer literals
- [Float](float-node.md): For floating-point literals
- [Boolean](boolean-node.md): For boolean literals
- [String](string-node.md): For string literals
- [Vec3f](vec3f-node.md) and [Vec3i](vec3i-node.md): For vector literals

## Example
Use Literal nodes to set parameters for other nodes:

1. Create a Literal node and set its value (e.g., the string "Hello, World!").
2. Connect this node to a [Print](print-node.md) node's `value` input.
3. When the workflow runs, it will print the constant string "Hello, World!".

Literal nodes are also useful for mathematical operations, conditional checks, and anywhere else where you need a fixed value in your workflow.

## Note
While Literal nodes are simple, they're crucial for providing constant inputs to more complex nodes and operations. They allow you to fine-tune your workflows with precise, unchanging values.
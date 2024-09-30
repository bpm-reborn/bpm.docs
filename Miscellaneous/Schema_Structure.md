Thank you for that clarification. I'll revise the node schema structure description to use YAML instead of JSON. This adjustment will make the guide more accurate and useful for BPM Reborn users.

# BPM Reborn: Node Schema Structure

## Introduction

In BPM Reborn, nodes are the fundamental building blocks of your mod's logic. Each node type is defined by a schema that describes its behavior, inputs, outputs, and how it interacts with the Lua runtime. Understanding the node schema structure is crucial for both using existing nodes effectively and creating custom nodes.

## Node Schema Overview

A node schema in BPM Reborn is a structured definition that includes:

- Metadata about the node
- Properties that can be configured
- Input and output edges
- The Lua source code that defines the node's behavior

This information is stored in YAML format and is used by the BPM Reborn system to generate the visual representation of the node, handle connections, and generate the appropriate Lua code.

## Schema Components

### Metadata

The metadata section provides general information about the node:

```yaml
name: ExampleNode
type: Function
category: Logic
description: An example node that demonstrates the schema structure.
```

- `name`: The unique identifier for this node type
- `type`: The general classification of the node (e.g., "Function", "Event", "Variable")
- `category`: Used for organizing nodes in the editor
- `description`: A brief explanation of the node's purpose

### Properties

Properties are configurable values that can be set in the node editor:

```yaml
properties:
  maxValue:
    type: float
    default: 100.0
    description: The maximum allowed value
  mode:
    type: enum
    options: 
      - Normal
      - Advanced
      - Expert
    default: Normal
    description: Operation mode
```

Each property has a type, default value, and description. The type can be standard (like float, int, string, boolean) or custom (like enum).

### Inputs

Inputs define the data that can be fed into the node:

```yaml
inputs:
  value:
    type: float
    description: The input value to process
  enable:
    type: exec
    description: Execution input
```

Inputs can be data inputs (like float, int, string) or execution inputs (type "exec").

### Outputs

Outputs define the data or execution paths that come out of the node:

```yaml
outputs:
  result:
    type: float
    description: The processed result
  onSuccess:
    type: exec
    description: Executed when operation succeeds
  onFailure:
    type: exec
    description: Executed when operation fails
```

Like inputs, outputs can be data outputs or execution outputs.

### Source

The source section contains the Lua code that defines the node's behavior:

```yaml
source: |
  local function ${NODE.name}(${value}, ${maxValue}, ${mode})
    if ${value} > ${maxValue} then
      ${EXEC.onFailure}
      return nil
    else
      local result = processValue(${value}, ${mode})
      ${EXEC.onSuccess}
      return result
    end
  end
```

The source code uses special placeholders:
- `${NODE.name}`: Replaced with the node's unique identifier
- `${propertyName}`: Replaced with the value of the specified property
- `${inputName}`: Replaced with the code to access the input value
- `${EXEC.outputName}`: Replaced with the code to trigger the specified execution output

## Example Node Schema

Here's a complete example of a node schema in YAML:

```yaml
name: ClampValue
type: Function
category: Math
description: Clamps a value between a minimum and maximum

properties:
  min:
    type: float
    default: 0.0
    description: Minimum allowed value
  max:
    type: float
    default: 1.0
    description: Maximum allowed value

inputs:
  value:
    type: float
    description: The value to clamp
  execute:
    type: exec
    description: Execution input

outputs:
  result:
    type: float
    description: The clamped value
  continued:
    type: exec
    description: Execution continues here

source: |
  local function ${NODE.name}(${value}, ${min}, ${max})
    local result = math.min(math.max(${value}, ${min}), ${max})
    ${EXEC.continued}
    return result
  end
```

## Custom Node Creation

To create a custom node:

1. Define the node schema following the YAML structure above
2. Register the node schema with BPM Reborn's node library
3. Implement any necessary Lua functions that your node calls
4. Test the node thoroughly in various scenarios

## Best Practices

1. **Clear Naming**: Use descriptive names for your node, properties, inputs, and outputs
2. **Comprehensive Descriptions**: Provide clear descriptions for each component of your node
3. **Input Validation**: Validate inputs in your Lua source to prevent errors
4. **Efficient Code**: Keep your Lua source code efficient, especially for nodes that may be called frequently
5. **Consistent Styling**: Follow consistent naming and styling conventions in your node schemas
6. **Documentation**: Maintain separate documentation for complex nodes or node libraries
7. **YAML Formatting**: Ensure proper YAML indentation and structure to avoid parsing errors

By understanding and following this node schema structure, you can effectively use existing nodes and create powerful custom nodes in BPM Reborn, enhancing your modding capabilities. The use of YAML makes the schemas more readable and easier to maintain compared to other formats.
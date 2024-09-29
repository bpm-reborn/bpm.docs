Here's a rewritten onboarding markdown file that describes Lua and workspace structure in depth, with improved formatting:

# BPM Reborn: Onboarding Guide

![BPM Reborn Logo](https://i.imgur.com/Ad1iQ6x.png)

## Table of Contents

1. [Introduction](#introduction)
2. [Lua Basics](#lua-basics)
3. [Workspace Structure](#workspace-structure)
4. [Node Graph System](#node-graph-system)
5. [Lua Integration](#lua-integration)
6. [Best Practices](#best-practices)

## Introduction

Welcome to BPM Reborn, a powerful core mod for Minecraft that revolutionizes modding through its advanced node graph system and Lua integration. This guide will help you understand the fundamentals of Lua programming and the structure of BPM Reborn workspaces.

## Lua Basics

Lua is a lightweight, efficient scripting language that forms the backbone of BPM Reborn's logic system. Here's a quick overview of Lua's key features:

### Variables and Data Types

```lua
-- Variables
local x = 10
local name = "Steve"

-- Data types
local number = 42
local text = "Hello, world!"
local boolean = true
local table = {1, 2, 3, key = "value"}
local func = function(a, b) return a + b end
```

### Control Structures

```lua
-- If statements
if condition then
    -- code
elseif other_condition then
    -- code
else
    -- code
end

-- Loops
for i = 1, 10 do
    print(i)
end

while condition do
    -- code
end

-- Functions
function greet(name)
    return "Hello, " .. name .. "!"
end
```

### Tables and Metatables

```lua
-- Tables (arrays and dictionaries)
local player = {
    name = "Alex",
    health = 20,
    inventory = {"sword", "pickaxe"}
}

-- Metatables (for OOP-like behavior)
local Player = {}
Player.__index = Player

function Player:new(name)
    local self = setmetatable({}, Player)
    self.name = name
    self.health = 20
    return self
end

function Player:takeDamage(amount)
    self.health = self.health - amount
end
```

## Workspace Structure

A BPM Reborn workspace consists of several key components:

1. **Nodes**: Visual representations of logic and functionality.
2. **Edges**: Connections between nodes that define data flow.
3. **Variables**: Global values accessible throughout the workspace.
4. **Events**: Trigger points for node execution.

### Workspace Hierarchy

```
Workspace
│
├── Nodes
│   ├── Events
│   ├── Logic
│   ├── Math
│   └── Custom Nodes
│
├── Edges
│
├── Variables
│
└── Events
```

## Node Graph System

BPM Reborn's node graph system allows for visual programming, similar to Unreal Engine's Blueprints. Here's how it works:

1. **Node Types**:
    - Event Nodes: Entry points for execution
    - Function Nodes: Perform specific operations
    - Variable Nodes: Read or write global variables
    - Custom Nodes: User-defined functionality

2. **Connections**:
    - Execution Flow: Determines the order of node execution
    - Data Flow: Passes data between nodes

3. **Execution**:
    - Starts at Event Nodes
    - Follows execution flow
    - Processes data through connected nodes

## Lua Integration

BPM Reborn translates the visual node graph into Lua code for execution. Here's an example of how a simple node graph might translate to Lua:

Visual Node Graph:
```
[Player Join Event] -> [Get Player Name] -> [Send Welcome Message]
```

Generated Lua Code:
```lua
local function Player_Join_Event_123()
    local player_name = Get_Player_Name_456()
    Send_Welcome_Message_789(player_name)
end

return {
    PlayerJoin = {Player_Join_Event_123}
}
```

## Best Practices

1. **Modular Design**: Break complex logic into smaller, reusable nodes.
2. **Clear Naming**: Use descriptive names for nodes, variables, and events.
3. **Comments**: Add comments to explain complex logic or intentions.
4. **Error Handling**: Implement error checking and graceful failure in custom nodes.
5. **Performance**: Be mindful of performance impact, especially in frequently executed nodes.
6. **Version Control**: Use version control systems to track changes in your workspaces.

By mastering Lua basics and understanding the workspace structure, you'll be well-equipped to create powerful and efficient mods using BPM Reborn. Happy modding!
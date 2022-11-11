# Gazebo No Physics Plugin

## Motivation

In many situations full physics simulation is overkill and only serves to complicate testing. It can be advantageous to only simulate object movement, or sensor input without solid body collisions.

## Goals

- The plugin shall disable the underlying physics engine in Gazebo such that objects will not react to forces or collisions.
- Gravity shall have no effect.

## Requirements

- The plugin shall be applied to the upper level world file.

```xml
<gazebo>
    <plugin name="gazebo_no_physics_world_plugin" filename="libgazebo_no_physics_world_plugin.so"></plugin>
</gazebo>
```

## Design

This plugin has been based on source code provided by Boeing, and migrated to ROS2. For further reference visit:

<https://gitlab.com/mtdi/pi9419/boeing/gazebo_no_physics_plugin>

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


# License

Copyright 2023 The Boeing Company

Licensed under the Apache License, Version 2.0 (the "License") with the following modification;
you may not use this file except in compliance with the Apache License and the following modification to it:

(Appended as Section 10)

By accepting this software, recipient agrees that the representations, warranties, obligations, and liabilities of The Boeing Company set forth in this software, if any, are exclusive and in substitution for all other all other representations, warranties, obligations, and liabilities of The Boeing Company.
Recipient hereby waives, releases, and renounces all other rights, remedies, and claims (including tortious claims for loss of or damage to property) of recipient against The Boeing Company with respect to this software.
The Boeing Company hereby disclaims all implied warranties, including but not limited to, all implied warranties of merchantability, fitness, course of dealing, and usage of trade.
The Boeing Company shall have no liability, whether arising in contract (including warranty), tort (whether or not arising from the negligence of The Boeing Company), or otherwise, for any loss of use, revenue, or profit, or for any other unspecified direct, indirect, incidental, or consequential damages for anything delivered or otherwise provided by The Boeing Company under this software.

You may obtain a copy of the original, unmodified License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
echo 

# Contributing

Any contribution that you make to this repository will
be under the Modified Apache 2 License, as dictated by that
[license](http://www.apache.org/licenses/LICENSE-2.0):

```
5. Submission of Contributions. Unless You explicitly state otherwise,
   any Contribution intentionally submitted for inclusion in the Work
   by You to the Licensor shall be under the terms and conditions of
   this License, without any additional terms or conditions.
   Notwithstanding the above, nothing herein shall supersede or modify
   the terms of any separate license agreement you may have executed
   with Licensor regarding such Contributions.
```

To contribute, issue a PR and @brta-jc (jason.cochrane@boeing.com)

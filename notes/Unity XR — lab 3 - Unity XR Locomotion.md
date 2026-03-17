---
id: p02l6fb85rnbbinc
type: NoteCard
createdAt: null
viewedAt: 2026-03-17T13:11:33.424Z
---

# Unity XR — lab 3 - Unity XR Locomotion
The XR Interaction Toolkit provides a set of components for locomotion.

Locomotion refers to the way users move around or navigate within a virtual environment (the XR experience).

The main components of locomotion are:

**Locomotion System**: This controls how the XR Origin (representing the user) can move or navigate in the virtual scene. It relies on XR Origin

**Continuous Dynamic Move Provider:** It lets the user smoothly move through the virtual environment over time.

**Continuous Turn Provider (replaced with Dynamic Move Provider in Unity 6)**: It allows the user to smoothly rotate over time, providing a more gradual and fluid turning motion.

**Snap Turn Provider**: It enables the user to rotate in fixed angles, providing a quick and *discrete* way to change their orientation in the virtual world.

**Grab Move Provider**: It allows the user to move in the virtual space in a way that responds to the movement of their controllers.

**Two-Hand Grab Move Provider**: This is similar to Grab Move, but it involves using both hands to not only move but also rotate and scale the user's position in response to the controller movements.
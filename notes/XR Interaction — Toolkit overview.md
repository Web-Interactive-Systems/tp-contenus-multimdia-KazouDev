---
id: olk6o9pvss70jmuk
type: NoteCard
createdAt: 2024-12-19T07:53:49.621Z
viewedAt: 2026-03-17T13:04:07.657Z
---

# XR Interaction — Toolkit overview
Interactions in a scene are based on two key elements:

-   **Interactors**: elements in the scene directly controlled by the user, typically through XR controller hardware, hand tracking, or touch screens on mobile AR devices. Interactors initiate interactions with interactable objects.
-   **Interactables**: the objects in a scene that the user can interact with. Interactable objects have states that indicate how they are being interacted with.

Every frame, the active interactors identify which interactable objects they can interact with.

Interactable objects enter the hover state and dispatch hover entered events, which we can use to provide feedback to the user that interaction is possible.

The user can then initiate selection of an interactable, the next phase of an interaction.
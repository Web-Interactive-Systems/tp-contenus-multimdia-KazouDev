---
type: NoteCard
createdAt: null
viewedAt: 2025-12-05T13:58:43.245Z
---

# unity xr template: goal manager
This code is a C# script written for the Unity game engine. It appears to be a part of an augmented reality (AR) onboarding system or tutorial. Let's break down the key components and functionality:

1.  **Goal Struct:**

    *   Defines a **`Goal`** struct, representing individual onboarding goals.
    *   Each goal has a type from the **`OnboardingGoals`** enum (such as **`Empty`**, **`FindSurfaces`**, or **`TapSurface`**) and a completion status.

2.  **GoalManager Class:**

    *   Manages the onboarding goals and their progression.
    *   Uses a queue (**`m_OnboardingGoals`**) to store the sequence of onboarding goals.
    *   Tracks the current goal, whether all goals are finished, the number of surfaces tapped, and the index of the current goal.
    *   Contains a list of **`Step`** objects, each representing a step in the onboarding process with associated UI elements.
    *   Exposes various serialized fields for UI elements, toggles, and other components.

3.  **Start Method:**

    *   Initializes various variables and components at the start of the script.
    *   Enqueues a sequence of onboarding goals into the **`m_OnboardingGoals`** queue.

4.  **OpenModal and CloseModal Methods:**

    *   Control the opening and closing of a modal window.

5.  **Update Method:**

    *   Called every frame.
    *   Calls the **`ProcessGoals`** method if not all goals are finished.
    *   In the Unity editor, allows for manually completing the current goal with the space key.

6.  **ProcessGoals Method:**

    *   Adjusts the UI and behavior based on the current onboarding goal.

7.  **CompleteGoal Method:**

    *   Handles the completion of a goal.
    *   Adjusts UI elements and activates/deactivates certain components.
    *   Enqueues the next goal if available.

8.  **TurnOnPlanes Coroutine:**

    *   Delays for a short time and then enables the ARPlaneManager.

9.  **DisableTooltips Method:**

    *   Disables tooltips based on the current goal.

10. **ForceCompleteGoal, ForceEndAllGoals, ResetCoaching Methods:**

    *   Methods to force complete goals, end all goals, and reset the coaching process, respectively.

11. **OnObjectSpawned Method:**

    *   Event handler for when an object is spawned.
    *   Counts the number of surfaces tapped and completes the goal if the required number is reached.

12. **TogglePlayer and TurnOnVideoPlayer Methods:**

    *   Control the visibility of a video player.
    *   The **`TurnOnVideoPlayer`** method positions and rotates the video player based on the camera's position and orientation.

The script seems to manage a step-by-step onboarding process, guiding the user through different goals in an AR environment, including finding surfaces and tapping on them. It uses various UI elements, toggles, and fades to enhance the user experience. The script also interacts with a video player and includes methods to force complete or reset the onboarding process.

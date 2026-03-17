---
id: m00v4n7o3cb488x6
type: NoteCard
createdAt: 2026-03-12T08:38:34.129Z
viewedAt: 2026-03-17T13:12:32.829Z
---

# 001 — Labs — Unity Designing XR Apps
# lab0: XR Design Space

## **XR Design Space**

The goal of this unit is try some XR apps, and to complete a design space for Designining XR Apps. The design space has dimensions, each with a set of options. Some dimensions are given to illustrate the idea. You can dimensions that fit.

-   Navigation

    -   …

-   Interaction

-   Modality

-   Sensing

-   3D Processing and Rendering

-   …

### **Testing students apps**

-   David VR
-   Collin VR
-   Théo VR
-   Aquarium VR

### **Study Hall**

### **Testing Unity collab template**

-   Create an app using the collaborative template (MR Multiplayers)
-   Deploy and test the scene

**Testing Unity XR interaction samples**

-   Clone : [**\[GitHub - Unity-Technologies/XR-Interaction-Toolkit-Examples\]**](https://github.com/Unity-Technologies/XR-Interaction-Toolkit-Examples)
-   Deploy and test the scene

### **Testing Unity MR template (Skip this one as need MetaQuest3 for MR)**

-   Create an app using the default VR template
-   Deploy and test the scene

***

## lab1.1: Setting up a sample VR scene

The goal of this unit is to set up a sample VR environment and import, and animate as 3D model inside the environment.

**Setting up a sample VR scene**

Please download the models from this link: <https://drive.google.com/file/d/1maIKrl0GAH8nef11funqlDx_8MMH_d6i/view?usp=drive_link>

-   Create a new project using the **VR Template** (you need to download the template the first time)
-   One way to build and deploy a unity scene is by connecting the headset (MetaQuest) to your machine
-   For the first time, you need to authorize the connection between the headset and your machine (use —Always Authorize)
-   Then, to build an app for MetaQuest, we need to swich the platform to Android
-   Deploy and test the scene

***

## lab1.2: Setting up a sample VR scene

**Organizing a Project**

-   Create an Assets folder named **\_App**
-   Inside the folder **\_App/**, create these folders: **Materials**, **Prefabs**, **Scenes**, and **Scripts**

**Adding a 3D Model a Project**

-   Drag and drop the Models folder inside Assets
-   Add the model Dolphin\_HL\_Ready to the scene
-   Adapt the Transform of the model

**Fixing the materials of the 3D model**

-   Notice that the materials of the model are not working fine (the color is Pink).
-   To fix the materials change their Shader into, for example, **Universal Render Pipeline/Lit.**
-   In the **Hierarchy**, expand the Dolphin model, and select Dolphin\_Body
-   In the **Inspector**, locate the shader, and change it to **Universal Render Pipeline/Lit**
-   Locate the Dolphin **eyes**, and do the same for their shader

**Testing the scene**

-   Deploy and test the scene
-   Notice that the model is not animated, it would be better if the model is animated
-   Add Animator component to the model
-   Locate the Dolphin\_Controller (inside Models/Animations/Dolphin\_Anim)
-   Drag and drop the Dolphin\_Controller into Controller slot of Animator component
-   Deploy and test the scene

***

## lab1.2: Setting up a mini VR Aquarium

The goal of this unit is to set up a sample mini VR Aquarium

-   Search for the aquarium model in the assets and add it to the to the scene
-   Notice the materials are not working —again they are pink
-   One of the best way to address this issue to use the proper shader that comes with materials
-   The materials of the aquarium are handled with package microsoft toolkit, so let us install the package

**Install the MRTK Graphics Tools package**

-   Check the docs: <https://github.com/microsoft/MixedReality-GraphicsTools-Unity>
-   Follow the steps in **Getting started with Graphics Tools** to install the package

***

## lab1.3: Setting up a mini VR Aquarium Scene

The goal of this unit is to set up a sample scene from scratch for a mini VR Aquarium

-   Create a new scene inside \_App/Scenes, call it MiniAquarium
-   Double click on the scene to open it in the Hierarchy
-   Delete existing Main Camera and Directional Light from the scene
-   Search for `XR Origin Hands (XR Rig)`in the assets and add it the scene
-   Reset the `Transform` of the XR Origin
-   Create an empty gameobject called UX (Reset its Transform)
-   Under UX add Aquarium model (remember, we added this before to our scene!)
-   Inside the scene, create an empty gameobject called `Environment`
-   Under Environment, use 3D cubes to create a a building: Floor and 4 Walls
-   Play with the Floor Walls to increase the space of the environment

**Study Hall**

PS. If you wanted to create advanced enviroments, you can install and use the package ProBuilder for Unity

***

## lab3: Setting up locomotion

The XR Interaction Toolkit provides a set of components for locomotion. Locomotion refers to the way users move around or navigate within a virtual environment (the XR experience).

The main components of locomotion are:

**Locomotion System**: This controls how the XR Origin (representing the user) can move or navigate in the virtual scene. It relies on XR Origin

**Continuous Dynamic Move Provider:** It lets the user smoothly move through the virtual environment over time.

**Continuous Turn Provider (replaced with Dynamic Move Provider in Unity 6)**: It allows the user to smoothly rotate over time, providing a more gradual and fluid turning motion.

**Snap Turn Provider**: It enables the user to rotate in fixed angles, providing a quick and *discrete* way to change their orientation in the virtual world.

**Grab Move Provider**: It allows the user to move in the virtual space in a way that responds to the movement of their controllers.

**Two-Hand Grab Move Provider**: This is similar to Grab Move, but it involves using both hands to not only move but also rotate and scale the user's position in response to the controller movements.

Because we used premade XR Origin Hands (XR Rig), locomotion is already setup

Let us inspect locomotion key components:

-   Inspect Locomotion inside XR Origin
-   Notice that Locomotion needs Locomotion Mediator component
-   Notice that Locomotion needs XR Body Transformer component
-   Inspect Turn and Move inside Locomotion
-   Build and test the scene

***

## lab4: Setting up teleportation

The XR Interaction Toolkit provides a set of components for teleportation. Teleportation is a way of navigation where the user jumps from one place to another in the virtual world.

There are two main components to enable teleportation:

**Teleportation Provider**: Allows the user to move instantly from one place to another within the XR environment as if they are teleporting. It relies on the **Locomotion System**.

**Teleportation Area**: This is an interactable. It enables teleportation for a GameObject.

Because we used premade XR Origin Hands (XR Rig), part of teleporation is already setup

Let us finalize teleportation:

-   Inspect Teleportation prefab inside XR Origin to get familiar with its components
-   Inspect the params of Teleportation Provider
-   Inspect Teleportation and notice that Locomotion inside the slot Mediator is Locomotion gameobject of the XR Origin
-   Add component teleportation area to the Floor gameObject and set interaction layer mask to teleport
-   Build and test the scene

***

## lab5: Setting up grab interaction

Let us set up the grab interaction to the dolphin gameObject:

-   Add the dolphin to the scene if is not already in the scene
-   Attach the Rigidbody component to dolphin gameObject
-   Attach the BoxCollider component to dolphin gameObject
-   Adjust the BoxCollider around the dolphin gameObject
-   Attach the XR Grab Interactable component to dolphin gameObject 
-   Build and test the scene

***

## lab6: Setting up affordances

Affordance is the type of feedback the user receives when interacting with objects in the scene. This could be color or audio (There is also an automatic haptic in Meta Quest).

Let us add two affordances: color and audio to the dolphin

-   Add a gameObject to the dolphin gameObject, call it “Interaction Affordance”
-   Attach the script component “XR Interactable Affordance State Provider” to the Interaction Affordance
-   Uncheck Ignore Focus Events in the script properties
-   Add a gameObject to the Interaction Affordance gameObject, call it “Color Affordance”
-   Add a grameObject to the Interaction Affordance gameObject, call it “Audio Affordance”
-   Attach Color Material Property Affordance Receiver to the Color Affordance (This will automatically add Material Property Block Helper component)
-   Inspect Color Affordance, and drag and drop the Dolphin\_Body into the slot ‘Renderer’ of Material Property Block Helper
-   Inspect Color Affordance, and drag and drop the Interaction Affordance gameObject into the slot of ‘Affordance State Provider’ of Color Material Property Affordance Receiver
-   Click on the donut of Affordance Theme Datum of Color Material Property Affordance Receiver and search for ColorAffordanceTheme
-   Inspect Color Affordance and check the box labeled **Replace Idle State Value With Initial Value** to ensure the original color of the material is used when the state returns to idle.
-   Attach Audio Affordance Receiver to the Audio Affordance gameObject
-   Drag and drop the Interaction Affordance gameObject into the slot of ‘Affordance State Provider’ of Audio Affordance Receiver
-   Click on the donut of Affordance Theme Datum of Audio Affordance Receiver and search for AudioAffordanceTheme
-   Build and test the scene

Learn more:

-   [\[https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@3.0/manual/affordance-system.html\]](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@3.0/manual/affordance-system.html)

***

## lab7: Setting up a lever

**Setting up a lever**

Import this package:

**Ne pas importer** : [\[https://drive.google.com/file/d/1o14\_\_6NyXJ\_yZSncXqwjER-VyDfEneQN/view?usp=drive\_link\]](https://drive.google.com/file/d/1o14__6NyXJ_yZSncXqwjER-VyDfEneQN/view?usp=drive_link)

-   Aller dans XR-Interactions-Exemples

-   Chercher “Lever”

-   Clic droit sur le prefab

-   “Export package…” 

-   Décocher “Include all scripts”

-   Enregistrer quelque part sur son pc

-   Retourner sur MR-Template

-   Dans assets, clique droit puis import package > custom package

-   Sélectionner l’export du levier précédemment fait

-   Add a GameObject Station to the scene.

-   Reset the transform of the Station GameObject

-   Add a cube to the station. The cube will be the base of the station.

-   Add **lever** prefab (pas le model) to the scene (search in assets by “lever”).

-   Make sure that the lever is well scaled and placed on the top of the base (cube).

-   Analyze the script **XR Lever**, attached to Lever, in particular, the function **onLeverActivate**.

-   Add a Particle System that releases particles when the **lever is activated**.

    -   create new empty game object
    -   rename it particules 
    -   right click on it 
    -   go to effects => particules system
    -   deactivate play on awake or it will play as soon as the project is started

-   Stops particles when the lever is deactivated, dans les paramètres du levier : 

    -   OnLeverActivate, faire glisser le particle system, mettre [ParticleSystem.play](http://ParticleSystem.play)
    -   OnLeverDeactivate, faire glisser le particle system, mettre ParticleSystem.stop

PS: “Si le levier ne marche pas, vérifier que le stickhandle est dans le slot du handle du lever”

***

## lab8: Setting up a wheel

-   Do the same as in Unit 3 to add the wheel prefab
-   Analyze the script **XRKnob** attached to the wheel prefab
-   In particular, the function **onValueChange**.

***

## lab9: Setting up a climb

-   Create a gameObject called Climb

-   Search for the prefab Ladder and add it to the Climb gameObject

-   Import the asset Climbing Wall using the link below

    -   [\[https://drive.google.com/file/d/1PH9V-VD41P6b\_nOZTfzXrU8XFUTnHfVC/view?usp=drive\_link\]](https://drive.google.com/file/d/1PH9V-VD41P6b_nOZTfzXrU8XFUTnHfVC/view?usp=drive_link)

-   Search for the prefab Climbing Wall among the assets and add it under the Climb gameObject

-   Notice that the handles of the ladder have Climb Interatable component

-   Notice that the routes of the wall have Climb Interatable component

-   Add Climb prefab to the XR Locomotion

Todo

[\[https://docs.google.com/document/d/1mtyJnhl\_9htLskLBJkOG2q796429YDnedtuKBWI\_PLk/edit?usp=sharing\]](https://docs.google.com/document/d/1mtyJnhl_9htLskLBJkOG2q796429YDnedtuKBWI_PLk/edit?usp=sharing)
# ue-procedural-limbs
Procedural animation for insectoid limbs (WIP) brought to UE4 **inspired by [/u/happygamedev](https://old.reddit.com/user/happygamedev)'s post on reddit.**

Only the root component of an actor is being translated in world-space and the limbs are automatically animated accordingly using IK.
The body also reacts automatically to the limb movement by leaning and (spring-based) raising/lowering.

# Demo
*The demo gif is in 15fps to keep the file size down*
![gif](Promo/proc-anim.gif)

# Goals
This should eventually become a pluggable C++ component-suite, that allows you to add/create insectoid-like limbs on your models, without having to animate them by hand.
Ideally this could overcome challenges in dynamic gameplay systems, where fully pre-made animations may be a limiting factor.

# Current state
Everything right now is in Blueprints. I plan to migrate this over to C++ once I have a clearer plan of what features I want to consider.

There are 2 actor components that do the job right now: `LimbAnimator` and `LimbCoordinator`.
`LimbAnimator` animates a single limb, whereas `LimbCoordinator` tries to coordinate all the limbs movements in a sensible way, i.e. preventing simultaneous movement of neighboring limbs.

# TODOs
- [ ] Prevent overlaps of limbs with other geometry
- [ ] Allow climbing walls (or at least prevent violent glitching close to walls)
- [ ] Create a new component, that supports animating existing limbs on the model/skeleton.
- [ ] Experiment with blending between multiple animations (e.g. idle animations)

# Public/Private Resources

SC defines **public** as:

> Referenceable/interactable by all namespaces as well as in-game (when applicable).

And conversely, **private** as:

> Strictly only referenceable/interactable within the defining namespace.

*In other words, SC enforces that private resources do not exist outside of the namespace that they are defined in.*

## Classification

**All resources** defined in your datapack's primary namespace must be classified as either public or private.

### Player Interactable Behavior

Any resource that represents behavior that the player can directly interact with must be public; a few examples include:

* Loot tables dropped by entities or contained in chests.
* All recipes (that are not strictly impossible).
* Advancements that are announced or in the advancement screen.
* Dimensions that the player can visit (as well as the dimensions' associated resources).
* Structures that are placed/generated in any dimension that the player can visit.
* Enchantments that are visible to the player and/or fit into the standard enchanting system.

### Functions

For now, do not worry about functions; you may leave the `function` registry as is. Functions will be covered on their [dedicated page](TODO) in this guide.

### Other Resources

For all other resources, public/private classification is to your discretion.

With that being said, resources are generally expected to be public unless they have zero reasonable usage outside of your datapack's primary namespace. Recall that private resources are *completely inaccessible* to other namespaces/datapacks; they cannot modify, append to, or even read/reference these resources.

*If you are still unsure if a resource should be public or private, a good informal test is ask yourself "Would it make sense for this resource to exist under the `minecraft` namespace, given my datapack was built into Minecraft?" If the answer is yes, it should be public.*

## Seperation

Move all private resources to the directory `_` in their respective registry (i.e. `<registry>/<path>/<resource>` -> `<registry>/_/<path>/<resource>`) and ensure that all public resources are outside of this directory. Refactor references to these resources accordingly.

---

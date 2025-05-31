# Primary Namespace

## Definition

> A **primary namespace** is a datapack namespace that contains otherwise undefined registry resources (functions, recipes, advancements, etc.).
 
Importantly, this does not include overwriting or appending to already existing resources (e.g. adding a block to `#minecraft:infiniburn_overworld` or modifying the `minecraft:torch` recipe would not make `minecraft` a primary namespace of your datapack).

*A datapack namespace is any directory in a datapack's `data` directory.*

## Requirements

Under SC, your datapack must have **exactly one** primary namespace, and it must:

* Not be `minecraft` or `slimecore`.
* Not contain any `.` (period) characters.
* Not start with a `-` (dash) or `_` (underscore).
* Be 3+ characters in length.

While not explicitly required, it is expected that it is follows [good naming practices](TODO).

If your datapack is found to have multiple primary namespaces, see *[Dealing With Multiple Namespaces](TODO)*.

Note that defining *anything new* in the `minecraft` namespace, even if it may seem reasonable (ex: defining `minecraft/recipe/slime_ball.json`) would make `minecraft` a primary namespace (which is invalid).

*If your datapack depends on other datapacks, assume that the dependencies' resources are already defined when evaluating your datapack's namespaces (dependencies will be covered later in this guide).*

**If your datapack meets all of these requirements, you may skip to the [next section](./slimecore.md).**

## Dealing With Multiple Primary Namespaces
Ultimately, the two strategies for handling multiple primary namespaces are:

#### Splitting
Turning a primary namespace into it's own datapack, then declaring it as a dependency *(just as a mental/text note for now, official dependency declaration will be explained [later](TODO))* of the original datapack. Splitting is best for namespaces that are **not closely tied** to any one namespace and/or can **realistically be re-used in the future**.

#### Merging
Simply moving all of one namespace's resources into another namespace, effectively merging the two. Merging is best for "helper" or utility namespaces that are **closely tied/related** to others.

*Splitting tends to be the easier option, however it is recommended to do what makes the most sense to you as a datapack developer.*

### Example:

Given datapack with 3 primary namespaces:

* `math`: contains general math functions.
* `util`: contains utility resources for `coolcats`; references resources from `math` and `coolcats`.
* `coolcats`: contains gameplay related resources, is the "core" of this datapack; references resources from `util` and `math`.

The following would be a reasonable process:

1. **Merge `util` into `coolcats`**.
    1. Move all resources such that `util/<registry>/<resource>` becomes `coolcats/<registry>/_/util/<resource>` *(The `_/` indicates private, explained [later](TODO)*).
    * Delete the `util` namespace.
  
* **Split `math` into it's own datapack**.
    1. Create a new datapack.
    2. Move `math` into the new datapack's `data` directory.
    3. Rename `math` to something less generic to avoid namespace clashes with other packs (ex: `joemath` if the developer's name was Joe).

---

## Good Namespace Naming
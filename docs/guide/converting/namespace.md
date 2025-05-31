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

If your datapack meets all of the above requirements, you may skip to the [next section](./slimecore.md).

## Dealing With Multiple Primary Namespaces
Ultimately, there are two strategies for dealing with multiple primary namespaces.

**Splitting:** Turning a primary namespace into it's own datapack and declaring it as a dependency of the original datapack *(an informal text note will suffice for now. dependency declaration will be explained [later](TODO))*.

**Merging:** Moving all of one namespace's resources into another namespace.

Splitting tends to be the easier option, and is recommended for namespaces that can realistically be re-used in the future. Merging is best for "helper" or utility namespaces that reference or are closely related to the namespace(s) they are referenced by.

### Example

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
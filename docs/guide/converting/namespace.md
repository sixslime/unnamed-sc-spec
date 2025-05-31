# Primary Namespace

SC defines a **primary namespace** as:

> A namespace that contains/defines otherwise undefined resources (functions, recipes, advancements, etc.).

Importantly, this does not include overwriting or appending to already existing resources.

*For example, appending to `minecraft/tags/block/infiniburn_overworld.json` or overwriting `minecraft/recipe/torch.json` would not make `minecraft` a primary namespace of your datapack; however, defining `minecraft/recipe/slime_ball.json` would, because `minecraft/recipe/slime_ball.json` is not defined by default.*


## Requirements

Under SC, your datapack must have exactly one primary namespace, and it must:

* Be 3+ characters in length.
* Not contain any `.` (period).
* Not start or end with `-` (dash) or `_` (underscore).
* Not be `minecraft` or `slimecore`.

Also, while not explicitly required, it is expected that it follows [good naming practices](TODO).

Per these requirements, If your datapack defines any resources in the `minecraft` namespace that do not exist by default, you must move them to your datapack's primary namespace.

If your datapack depends on other datapacks, assume that the dependencies' resources are already defined when evaluating these requirements *(dependencies will be covered [later](TODO))*.

If your datapack meets all of the above requirements, you may go to the [next page](./slimecore.md).

## Dealing With Multiple Primary Namespaces
Two main strategies can be employed if your datapack contains multiple primary namespaces.

**Splitting:** Giving a namespace it's own datapack and declaring it as a dependency of the original datapack *(an informal text note will suffice for now. dependency declaration will be explained [later](TODO))*.

**Merging:** Moving all (new/defined) resources from one namespace into another namespace.

Splitting is recommended for namespaces with resources that can realistically be re-used in the future (and tends to be the easier option). Merging is best for "helper" or utility namespaces that reference or are closely related to the namespace(s) that they are referenced by.

As an example, imagine a datapack with 3 primary namespaces:

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

TODO

## Good Namespace Naming
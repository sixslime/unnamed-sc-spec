# Manifest Function

SC defines a **manifest function** as:

> A function that is included in the function tag `#slimecore:manifest` that calls `slimecore:manifest`.

Under SC, your datapack must define exactly one manifest function.

*Per this requirement, similar to how datapacks practically always include the `minecraft` namespace (to append to `#minecraft:tick`/`#minecraft:load`), SC packs must always include the `slimecore` namespace (to append to `#slimecore:manifest`).*

## Creation

Create a new function in your datapack's primary namespace to be your datapack's manifest function *(A reasonable path for this is `<primary namespace>:_/manifest.mcfunction`)*.

You can use the following as a template manifest function:
```mcfunction
data modify storage slimecore:in manifest.pack set value "<PRIMARY NAMESPACE>"
data modify storage slimecore:in manifest.version set value {major:1, minor:0, patch:0}
data modify storage slimecore:in manifest.display.name set value "<DISPLAY NAME>"
data modify storage slimecore:in manifest.display.summary set value "<1 SENTENCE LENGTH SUMMARY PHRASE>"
data modify storage slimecore:in manifest.url.this set value "<URL TO THIS VERSION>"
data modify storage slimecore:in manifest.url.latest set value "<URL TO LATEST VERSION>"
data modify storage slimecore:in manifest.author set value {name:"<YOUR NAME/ALIAS>", url:"<YOUR URL>"}

data modify storage slimecore:in manifest.library set value false
data modify storage slimecore:in manifest.abstract set value false

data modify storage slimecore:in manifest.expected_order set value {load:1b, tick:1b}

data modify storage slimecore:in manifest.dependencies set value []
data modify storage slimecore:in manifest.supports set value []
data modify storage slimecore:in manifest.implements set value []

function slimecore:manifest
```

In order to comply with SC, your datapack's manifest function must have all inputs properly set *(see the second section of this page)*. For the purposes of this guide however, the only input you need to set right now is `pack`, which **must** be set to the name of your datapack's primary namespace.

Append the manifest function to `#slimecore:manifest` by including it in your datapack's `slimecore/tags/function/manifest.json`.

At this point, your datapack should function as it did originally after reloading your world.

---

TODO

`#slimecore:manifest` must only contain manifest functions.

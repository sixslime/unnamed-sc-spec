# Entrypoints

> SC does not permit the direct modification of the function tags `#minecraft:load` or `#minecraft:tick`.

Instead, these function tags can be defined in a datapack's primary namespace:

1. `#<primary namespace>:pre_load`
* `#<primary namespace>:load`
* `#<primary namespace>:post_load`
* `#<primary namespace>:tick_start`

These tags will be automatically executed upon world reload in the shown order.

## Load

If your datapack includes `#minecraft:load`, move it to `#<primary namespace>:load`.

### Pre/Post Load
Standard datapacks do not need to define `pre_load`/`post_load`, however if your datapack uses a loading method that includes it, such as [lantern load](TODO), (and your datapack does include `pre_load`/`post_load` functions), you can define the function tags `#<primary namespace>:post_load` and `#<primary namespace>:pre_load`.

## Tick

If your datapack includes `#minecraft:tick`, move it to `#<primary namespace>:tick_start`.

Unlike `#minecraft:tick` however, `#<primary namespace>:tick_start` will **only execute once**.

Your datapack's tick function(s) are expected to *schedule themselves* (include `schedule function <self> 1t`) in order to create a tick loop.

## Manifest Required
If you reload your world after making the changes explained above, you will notice that your datapack's entrypoint functions are not executed; this is expected behavior. After you install SlimeCore and create your datapack's manifest, your datapack's entrypoint functions will execute as expected.

---

## Scheduling
It is an expectation that **all** of your datapack's self-scheduling functions are both cleared and started via `tick_start`. blah
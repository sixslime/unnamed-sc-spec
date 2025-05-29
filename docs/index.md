# Introduction

Welcome to the description and partial guide/documentation to an unnamed datapack specification, further referred too as **SC**. While SC itself is hypothetically complete, these docs only serve to express the idea of SC, not as definitive documentation *(see [Meta Information](meta.md))*.

Datapacks that follow SC are referred to as **SC packs**.


## What is SC?
SC is a specification for datapacks--that is, a set of documented rules that can be explicitly enforced across a datapack's contents and file structure.

SC is designed to achieve exactly one objective:
> Make developing, publishing, and using datapacks published by others as **painless as possible**.

It is designed to achieve this objective while being (in order of priority):

1. Realistically followable with **no** third party programs.
2. Robust as possible.
3. Unintrusive as possible.
4. Intuitive as possible.

## Who Is It For?
SC is ideal for experienced datapack developers that desire to use datapacks created by others and/or publish their own datapacks for others to use.

With that being said, SC can practically benefit **any player** that plays with more than one datapack in their world(s).

## What Exactly Does It Do?
Some key features of SC packs are:

#### Pack(age) Manifests

* Proper versioning.
* Proper authoring and descriptive information.
* Proper dependencies of other SC packs.
* Ability to define abstract interfaces (to be implemented by other packs).

#### Indication Of Public And Private

* File structure defining what can and cannot be accessed by other datapacks.
* Methods for indicating custom/private in-game behavior (custom items, entities, etc.)

#### Near-Impossible Cross-Pack Interference

* Explicitly defined `load` and `tick` ordering relative to other SC packs.
* Naming rules for almost everything, ensuring that no two resources interfere.
* Very clear public/private seperation (making unintended interactions very unlikely).

#### A Clean Experience
* Consistent public function documentation and input/output methods.
* Consistent and defined configuration options.
* Safe and automatic uninstallation.
* Explicitly defined storage data schema and documentation.
* Rich and explicit definitions for custom NBT types.



## Does It Require Any Downloads?
It would be dishonest to omit that SC requires the download of **SlimeCore**, a single datapack that acts as an orchestrator for any world that contains SC packs.

Before you leave immediately, please consider the following:

* SlimeCore has **zero performance impact** beyond the single `/reload` tick.
* SlimeCore has **zero gameplay impact**.
* Many awesome features that SC provides would not be possible without some sort of required datapack dependency.

### Isn't That Third Party?
Technically yes, a datapack is third party, but it is not a *program*. What SC ultimately means by "realistically followable with no third party programs", is that you should not need (or be practically required) to use a program or medium outside of what is officially supported by Minecraft.

*An example of such a third party program/tool is [Beet](https://github.com/mcbeet/beet). As awesome as it is, Beet requires the usage of python (among other things), which is obviously external to Minecraft.*

## Why Should I Follow SC?

In general, abiding by a strict rules may seem like an uneccessary hassle, and it may be if you are the *only one* abiding by them. However, if *multiple people* choose to follow the same set of rules, each person knows exactly what to expect from the others, and ideally, the benefits of this mutual understanding (especially over time) far outweigh the overhead of abiding by such rules.

Regarding SC specifically, SC is designed such that: In addition to being inherently understood on a base level by other SC developers, SC packs share a mutual understanding between *themselves*. In other words, SC maximizes compatibility and minimizes interference between SC packs, even if they do not explicitly know of each other. Thus, even if you are keen on being a solo developer who never uses anyone else's work, consider that following SC may benefit players that want to add your datapack to their world(s) alongside other datapacks.

### If You Are A Beginner To Commands:
It is actually **not** recommended that you follow SC. Trying to learn SC (or any sort of standard) before you have a basic understanding of commands is likely to only add further confusion.

However, if you are only new to **datapacks**, but somewhat experienced with commands, consider trying SC, it does not introduce anything unorthodox or against "normal" datapack structure (and may implicitly teach you good practices).

### Why Not Something Else?
For the same reason SC was made initially: *because there is nothing else.*

At the time of writing, the generally accepted standard of datapacks are a collection of good practices/conventions that are largely unspoken and/or not formally documented. This leads to an environment where it is usually a headache (or worse) to integrate someone elses work/datapack with your own.

SC aims to be a step toward a datapack ecosystem where developers can share their work and use others' shared work efficiently and fearlessly. Whether this is directly through widespread adoption of SC or through other means is not important, what matters is that *something* is done.


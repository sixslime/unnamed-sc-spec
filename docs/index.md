# Introduction

Welcome to the description and partial guide/documentation to an unnamed datapack specification, further referred too as **SC**. While SC itself is hypothetically complete, these docs only serve to express the idea of SC, not as definitive documentation *(see [Meta Information](meta))*.

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
* Ability to define abstract (to be implemented by other packs) interfaces.

#### Indication Of Public And Private

* File structure defining what can and cannot be accessed by other datapacks.
* Methods for indicating custom/private in-game behavior (custom items, entities, etc.)

#### Near-Impossible Cross-Pack Interference

* Naming rules for almost everything, ensuring that no two resources interfere.
* Very clear public/private seperation, making accidental interference extremely unlikely.

#### Standardized Public Definitions
* Consistent public function documentation and input/output methods.
* Consistent 
* Explicitly defined storage data schema and documentation.
* Ability to define, reference, and document custom NBT types.

And much more.

## Does It Require Any Downloads?
It would be wrong to omit that SC requires the download of **one datapack**, SlimeCore, for any world that contains SC packs. SlimeCore acts as an "orchestrator" for SC packs.

Before you leave immediately, please consider the following:

* SlimeCore has **zero performance impact** beyond the single `/reload` tick.
* SlimeCore has **zero gameplay impact**.
* Many awesome features that SC provides would not be possible without some sort of required datapack dependency.

### Isn't That Third Party?
Technically yes, a datapack is third party, but it is not a *program*. What SC ultimately means by "realistically followable with no third party programs", is that you should not need (or be practically required) to use a program or medium outside of what is officially supported by Minecraft.

*An example of such a third party program/tool is [Beet](https://github.com/mcbeet/beet). As awesome as it is, Beet requires the usage of python (among other things), which is obviously external to Minecraft.*










## Why Should I Use It?
Abiding by a set of rules may seem like an uneccessary hassle, and it may very well be if you are the *only one* abiding by them. However, if *multiple people* choose to follow the same set of rules, each person knows exactly what to expect from the others, and ideally, the benefits of this mutual understanding (especially over time) far outweigh the overhead of abiding by such rules.





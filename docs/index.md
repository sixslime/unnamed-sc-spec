# What Is SC?

SC is a specification for datapacks--that is, a set of documented rules that can be explicitly enforced across a datapack's contents and file structure.

Through widespread compliance, SC is designed to achieve exactly one objective:
> Make developing, publishing, and using datapacks published by others as **painless as possible**.

It is designed to achieve this objective while being (in order of priority):

1. Practically implementable with **no** third party programs.
2. Robust as possible.
3. Unintrusive as possible.
4. Intuitive as possible.

## Who Is It For?

SC is ideal for **experienced datapack developers** who desire to use datapacks created by others and/or publish their own datapacks for others to use.

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
* Very clear public/private separation (making unintended interactions very unlikely).

#### A Clean Experience

* Consistent public function documentation and input/output methods.
* Consistent and defined datapack configuration options.
* Safe and automatic uninstallation.
* Explicitly defined storage data schema and documentation.
* Rich and explicitly defined custom NBT types.

## Does It Require Any Downloads?

It would be dishonest to omit that SC requires the download of **SlimeCore**, a single datapack that acts as an orchestrator for any world that contains SC packs.

Before you dismiss SC, consider the following:

* SlimeCore has **zero performance impact** beyond the single `/reload` tick.
* SlimeCore has **zero gameplay impact**.
* Many awesome features that SC provides depend on an orchestration system.

### Isn't That Third Party?

Technically yes, a datapack is third party, but it is not a *program*. What is meant by "practically implementable with no third party programs", is that you should not need (or be practically required) to use a program or medium outside of what is officially supported by Minecraft. Further, this should also imply that existing third party programs can trivially integrate with SC.

*An example of such a third party program/tool is [Bolt](https://github.com/mcbeet/bolt). As awesome as it is, Bolt requires the usage of python (among other things), which is obviously external to Minecraft.*

## Where Do I Start?

TODO



# 关键遗迹 · 主世界 Overworld · Minecraft Wiki 条目

> 本文件属于 **Remnant / Echo 模组资料汇编** 的一部分。
> 所有内容均为原文引用，不做任何改写或描述，每段引用后均标注来源链接。

---


### Stronghold – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Stronghold>
- **页面摘要**：A stronghold is an underground structure in the Overworld, and is the only place where an End portal can be found. Strongholds can be located by using an eye of ender.

**原文引用：**

> A stronghold is an underground structure in the Overworld, and is the only place where an End portal can be found. Strongholds can be located by using an eye of ender.

> In Java Edition, each stronghold altar chest contains items drawn from 2 pools, with the following distribution:

> In Java Edition, each stronghold storeroom chest contains 1–4 item stacks, with the following distribution:

> Bedrock Edition: Config edit | edit source] Java Edition: [NBT Compound / JSON Object] Structure configuration [String] type: minecraft:stronghold

> Fields common to all structures see Template:Nbt inherit/structure/template[show]

> Legacy Console Edition edit | edit source] New Nintendo 3DS Edition edit | edit source] The first image of a stronghold that Jeb posted

> The first image of a stronghold that Notch posted

> Stronghold markers in Beta 1.9 Prerelease 3

> A stronghold generated on Superflat using Customization GUI in 12w40a and 12w40b.

> The side view of an uncovered stronghold

> Overhead view of an uncovered stronghold

> Top view of an uncovered stronghold

> Issues relating to "Stronghold" are maintained on the bug tracker. Issues should be reported and viewed there.

> There are exactly 233 bookshelves in a large library, yielding 699 books if mined without Silk Touch, which is 10 stacks plus 59 left over.

> Along with some other older structures, strongholds do not generate with air inside them.



### End portal – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/End_portal>
- **页面摘要**：An End portal is a naturally-occurring generated structure that is used to travel into the End. It can only be found in the portal room of a stronghold.

**原文引用：**

> In Survival mode, the player must venture to a stronghold to activate a pre-existing End portal, as End portal frame blocks cannot be obtained naturally. The portal is activated when an eye of ender has been placed in each of the End portal frame blocks, generating 9 End portal blocks within the structure. Eyes of ender cannot be removed from End portal frames.

> In Creative mode, the player can construct an End portal by placing 12 End portal frames in a ring enclosing an open 3×3 square and placing an eye of ender in each one. In order to activate, the End portal frames must be oriented correctly; the front face of each portal block must be pointed inward toward the 3×3 portal area. This can be achieved by the player standing in the center of the portal area and rotating to place the frames in a ring around them.

> The End portal blocks do not depend on the End portal frame to exist; thus, one may create standalone portals with commands or by breaking the frames.[1]

> In Java Edition, it is possible to construct an End portal which generates its End portal blocks outside of its structure. Due to the fact that the End portal generation has the same mechanism as iron golem and snow golem, the game allows the End portal frame arrangement to be rotated.

> Thus, in Java Edition, a valid End portal should obey these three rules:

> Any three End portal frames within one edge must have the same facing.

> Opposite edges must have opposite facing.

> With a valid End portal, one can refer the corner between the edges facing west and north as its "structural origin". After 12 End portal frames have all been filled with eye of ender, if any End portal frame within the 5x5x5 cube at the north-west-down of the origin, which is not necessarily a part of the structure, is filled with an eye of ender, the End portal is activated, generating 9 End portal blocks at the northwest of the origin (not always within the structure).

> Since rotation along X and Z axis is allowed, one can even construct a standing End portal frame.

> Then rotated 90° CCW along Y-axis

> Cannot activate automatically.

> Place a frame block within detection range

> and fill it to manually activate.

> There are 24 possible End portal frame configurations in Java Edition in total. 8 of them are flat, 8 of them are standing in XY-plane, 8 of them are standing in ZY-plane.

> End portals are found within the portal room of a stronghold, hanging horizontally over a pool of lava, with a staircase leading up to the portal. A monster spawner spawning silverfish sits in the staircase. Each individual End portal frame block has a 10% chance of containing an eye of ender, as determined by the world seed. This means there is a one in 1 trillion chance for all 12 End portal frames to contain an eye of Ender, activating the portal upon initial generation. The frame has the highest probability of generating with a single eye of ender (37.7%), with probabilities dropping to 28.2% for zero, 23.0% for two, 8.52% for three, 2.13% for four, and a total of 0.433% for five or more. Because of the huge number of possible seeds, over 8 million seeds in Java Edition that generate portals with 12 eyes of ender are known.[2]



### End Portal Frame – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/End_Portal_Frame>
- **页面摘要**：An End portal frame is an indestructible block, 12 of which form an End portal. Eyes of ender must be inserted into all 12 empty frames (if not already present upon generation) for the portal to activate and allow passage into the End dimension.

**原文引用：**

> 12 End portal frames generate naturally to form the End portal in each stronghold End portal room, over a pool of lava with a staircase containing a silverfish monster spawner. The frames generate in a 5×5 square formation, with 3 frames on each side, without the corners. Each End portal frame generates facing inward, with a 10% chance of containing an eye of ender.

> Each stronghold contains an End portal. In Java Edition, each world contains exactly 128 strongholds, so a total of 1,536 End portal frames are generated. In Bedrock Edition, there are infinitely many strongholds in each world, so the number of End portal frames that may generate is also infinite. In Legacy Console Edition, there was only one End portal per world, so 12 End portal frames were generated.

> There is an extremely low chance (10-12 or 10-10% or one in a trillion) for all twelve End portal frames to be filled in strongholds.

> The chart below shows the probability of having each number of eyes of ender filled in (some values may be rounded).

> Calculating the chance for a specific amount of eyes generating is done with the probability mass function:

> P(X=number of eyes) = (12k)⋅0.1k⋅(1−0.1)12−k with k being the number of eyes.

> Using eyes of ender on End portal frames inserts them to the top of the frame if it is not inserted previously.

> An End portal frame has a front face that faces the player when placed. Although the facing is almost invisible (one can distinguish only 2 rotations of End portal frames), all End portal frames must be placed correctly and face inward in order to be able to activate the End portal, and if all of the frames have eyes of ender inserted, the portal activates, replacing the inner 3×3 space with End portal blocks.

> If an End portal is built in the End, entities are teleported back to the world spawn point in the Overworld, similar to the exit portal.

> End portal frames output a redstone comparator signal of 15 when an eye is present. If there is no eye in the frame, it outputs a signal of 0.

> End portals frames emit a light level of 1.

> End portal frames cannot be pushed by pistons. They also cannot be pushed nor pulled by sticky pistons.

> Legacy Console Edition edit | edit source] New Nintendo 3DS Edition edit | edit source] Data history edit | edit source] Java Edition edit | edit source] Bedrock Edition edit | edit source] Issues edit | edit source] Issues relating to "End Portal Frame" are maintained on the bug tracker. Issues should be reported and viewed there. Trivia edit | edit source] End portal frames were obtainable and could be placed facing in different directions in the April Fools' snapshot 22w13oneBlockAtATime.

> The End stone portion of the End portal frame side texture does not match up with the End stone block texture.

> An End portal, which had been activated by a player



### Ruined Portal – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Ruined_Portal>
- **页面摘要**：Normal

**原文引用：**

> Most ruined portal structures contain enough obsidian to make a complete portal, although in the smaller portals, there may not enough because each obsidian has a 15%‌[JE only] or 20%‌[BE only] chance to be replaced by crying obsidian.

> Bedrock Edition: Config edit | edit source] Java Edition: [NBT Compound / JSON Object] Structure configuration [String] type: minecraft:ruined_portal

> Fields common to all structures see Template:Nbt inherit/structure/template

> [NBT List / JSON Array] setups: (Cannot be empty) A list of ruined portal setups to randomly choose one from it. [Int] weight: The weight this ruined portal setup is chosen.

> [String] placement: Either on_land_surface, partly_buried, on_ocean_floor, in_mountain, underground, in_nether. Determines how the ruined portal is placed.

> [Float] air_pocket_probability: The probability that the ruined portal generates an air pocket around it. Value between 0.0 and 1.0 (inclusive).

> [Float] mossiness: Determines how mossy the ruined portal is, as an argument for minecraft:block_age processor. Value between 0.0 and 1.0 (inclusive).

> [Boolean] overgrown: Determines whether or not jungle leaves generate.

> [Boolean] vines: Determines whether or not vines generate on the ruined portal.

> [Boolean] can_be_cold: Determines whether or not lava and magma can be replaced with netherrack.

> [Boolean] replace_with_blackstone: Determines whether or not stone bricks in the ruined portal are replaced with their blackstone equivalents.

> Bedrock Edition edit | edit source] Issues edit | edit source] Issues relating to "Ruined Portal" are maintained on the bug tracker. Issues should be reported and viewed there. Gallery edit | edit source] Screenshots edit | edit source] Overworld edit | edit source] A ruined portal in a taiga biome

> A ruined portal found underground

> A giant ruined portal generated in a savannah next to a desert

> A ruined portal that generated in an abandoned desert village



### Desert Pyramid – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Desert_Pyramid>
- **页面摘要**：A desert pyramid or desert temple is an uncommon above ground structure found in desert biomes built mostly of sandstone and terracotta. The desert pyramid contains four loot chests hidden under the floor in the center, which are protected by a TNT trap, and a secret buried room to the side where archaeology...

**原文引用：**

> A desert pyramid or desert temple is an uncommon above ground structure found in desert biomes built mostly of sandstone and terracotta. The desert pyramid contains four loot chests hidden under the floor in the center, which are protected by a TNT trap, and a secret buried room to the side where archaeology can be performed by brushing the generated suspicious sand with a brush.

> The loot chances above are per chest. As each chest has a 2.4% chance to contain an enchanted golden apple for example, with four chests, each pyramid has about a 9% chance overall of having at least one.

> In Java Edition and Bedrock Edition, each desert pyramid suspicious sand contains 1 item stack, with the following distribution:

> Bedrock Edition: Config edit | edit source] Java Edition: [NBT Compound / JSON Object] Structure configuration [String] type: minecraft:desert_pyramid

> Fields common to all structures see Template:Nbt inherit/structure/template[show]

> Legacy Console Edition edit | edit source] New Nintendo 3DS Edition edit | edit source] The main room of a desert pyramid from older versions, where dyed wool could be found.

> A perfect naturally-generated double desert pyramid.

> A pyramid generated in a village.

> A desert pyramid that has a monster room generated inside it.

> Issues relating to "Desert pyramid" or "Desert temple" are maintained on the bug tracker. Issues should be reported and viewed there.

> A chamber inside in one of the two towers

> The chamber from the top floor

> A desert pyramid containing terracotta

> The treasure room inside the hidden lower chamber of the pyramid

> The nine TNT rigged under the stone pressure plate



### Jungle Pyramid – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Jungle_Pyramid>
- **页面摘要**：A jungle pyramid&#91;a&#93;, also known as a jungle temple, is an above ground structure found in jungle biomes built mostly of cobblestone and mossy cobblestone. The jungle pyramid contains two loot chests, one at the end of a hallway of arrow booby traps, and one hidden behind a lever puzzle.

**原文引用：**

> A jungle pyramid[a], also known as a jungle temple, is an above ground structure found in jungle biomes built mostly of cobblestone and mossy cobblestone. The jungle pyramid contains two loot chests, one at the end of a hallway of arrow booby traps, and one hidden behind a lever puzzle.

> In Java Edition, each jungle pyramid dispenser contains 1–2 item stacks, with the following distribution:

> Bedrock Edition: Config edit | edit source] Java Edition: [NBT Compound / JSON Object] Structure configuration [String] type: minecraft:jungle_temple

> Fields common to all structures see Template:Nbt inherit/structure/template[show]

> New Nintendo 3DS Edition edit | edit source] Legacy Console Edition edit | edit source] Issues edit | edit source] Issues relating to "Jungle pyramid" or "Jungle temple" are maintained on the bug tracker. Issues should be reported and viewed there. Gallery edit | edit source] A layer-by-layer layout of the jungle pyramid

> The front of the jungle pyramid

> The chest guarded by dispenser traps

> The secret door revealing the hidden chest in the chamber

> Hostile mobs can possibly spawn in the secret chamber of the pyramid, due to the lack of light inside.

> Rear view of a jungle pyramid generated on the water

> Frontal view of a jungle pyramid generated on the water

> A floating jungle pyramid in Java Edition

> The very rare occurrence of a desert pyramid generated where a jungle pyramid would have been

> A jungle pyramid generated in a house in a superflat desert village

> A jungle pyramid generated on a swamp hut in a superflat desert world



### Mineshaft – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Abandoned_Mineshaft>
- **页面摘要**：Mineshafts are common underground structures primarily found underground in the Overworld. They consist of interlinked 3×3 tunnels with incomplete rail lines running through them, with oak planks platforms bridging gaps or hanging in larger exposed caverns.

**原文引用：**

> A unique variant of mineshafts made out of dark oak wood can generate on the surface in badlands biomes.

> In Java Edition and Bedrock Edition, each mineshaft chest located in a sulfur cave contains items drawn from 3 pools, with the following distribution:

> Bedrock Edition: Config edit | edit source] Java Edition: [NBT Compound / JSON Object] Structure configuration [String] type: minecraft:mineshaft

> Fields common to all structures see Template:Nbt inherit/structure/template[show]

> [String] mineshaft_type: Either normal or mesa. normal for mineshaft made of oak, while mesa for mineshaft made of dark oak.

> Legacy Console Edition edit | edit source] New Nintendo 3DS Edition edit | edit source] Issues edit | edit source] Issues relating to "Mineshaft" are maintained on the bug tracker. Issues should be reported and viewed there. Trivia edit | edit source] The central room of a mineshaft never generates in the same chunk as (0, 0) in any Minecraft world.‌[Java Edition only]

> In LEGO Minecraft Micro World – "The Village", a mineshaft is beneath a village.[10]

> A view of a mineshaft generated in a default Minecraft world, shown in Spectator mode

> A mineshaft that generated directly above an aquifer

> A cave spider monster spawner in a mineshaft

> A mineshaft generated on a superflat using the customize feature

> A spider monster spawner which generated connected to a mineshaft. Check the image for seed and coordinates.

> A mineshaft, which generated at bedrock level, along with diamonds. Check the image for seed and coordinates.

> A triple canyon with a mineshaft at the bottom

> A cobweb generated in a mineshaft



### Trail Ruins – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Trail_Ruins>
- **页面摘要**：Trail ruins are buried structures that work as archaeological sites where suspicious gravel generates. They are found in heavily forested biomes and resemble ruined villages from a lost culture.&#91;1&#93;

**原文引用：**

> Trail ruins are buried structures that work as archaeological sites where suspicious gravel generates. They are found in heavily forested biomes and resemble ruined villages from a lost culture.[1]



### Suspicious Sand – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Suspicious_Sand>
- **页面摘要**：Suspicious sand is a fragile gravity-affected block found in various Overworld structures. It can be brushed to extract unique structure-dependent loot from it. It drops nothing if it breaks, and will break if it falls or is moved.

**原文引用：**

> Suspicious sand drops nothing when it's destroyed.

> Suspicious sand generates naturally in buried rooms under desert pyramids, as well as in the bottom of desert wells. It also generates within warm ocean ruins.

> When a brush is used on a suspicious sand, cracks start to appear on all sides of the block as the dusted block state of the block starts to increase. If the suspicious sand being brushed is naturally generated, an item gradually emerges from the side where the player starts brushing. After 96 (6+20+30+40 per stage) game ticks (4.8 seconds), the item is extracted, and the suspicious sand is converted into sand.

> If the player stops brushing a suspicious sand, the block remains in its half-excavated state for a few seconds, before gradually returning to its unexcavated state one stage at a time.

> The item obtained and the loot table of suspicious sand is dependent on which structure it has generated in. Items can be extracted only from naturally generated suspicious sand. When placed by the player, nothing is produced after brushing.

> In Java Edition and Bedrock Edition, each warm ocean ruins suspicious sand contains 1 item stack, with the following distribution:

> Suspicious sand is destroyed when the piston tries to push it. It can't be pulled by the sticky piston.

> Bedrock Edition: ↑ ID of block's direct item form, which is used in savegame files and addons.

> Block states edit | edit source] Java Edition: Bedrock Edition: Block data edit | edit source] Main article: Block entity format [NBT Compound / JSON Object] Block entity data

> Tags common to all block entities see Template:Nbt inherit/blockentity/template

> Tags common to all objects that use loot tables to produce items see Template:Nbt inherit/lootable/template

> [NBT Compound / JSON Object] item: The item in the block. May not exist. See item format.

> Prototype texture of suspicious sand[2]

> Prototype of suspicious sand being brushed

> Thrown Splash Potion Lingering Potion



### Suspicious Gravel – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Suspicious_Gravel>
- **页面摘要**：Suspicious gravel is a fragile gravity-affected block found in various Overworld structures. It can be brushed to extract unique structure-dependent loot from it. It drops nothing if it breaks, and breaks if it falls or is moved.

**原文引用：**

> Suspicious gravel drops nothing when it's destroyed.

> Suspicious gravel generates naturally in cold ocean ruins. Additionally, some of the gravel within trail ruins is replaced with suspicious gravel upon generation.

> When a brush is used on suspicious gravel, cracks start to appear on all sides of the block as the dusted block state of the block starts to increase. If the suspicious gravel being brushed is naturally generated, an item gradually emerges from the side where the player starts brushing. After 96 (6+20+30+40 per stage) game ticks (4.8 seconds), the item is extracted, and the suspicious gravel is converted into gravel.

> If the player stops brushing a suspicious gravel, the block remains in its half-excavated state for a few seconds, before gradually returning to its unexcavated state one stage at a time.

> The item obtained and the loot table of suspicious gravel depends on the structure where it had generated. Items can be extracted only from naturally generated suspicious gravel. When placed by the player, nothing is produced after brushing.

> In Java Edition and Bedrock Edition, each trail ruins common suspicious gravel contains 1 item stack, with the following distribution:

> Bedrock Edition: ↑ ID of block's direct item form, which is used in savegame files and addons.

> Block states edit | edit source] Java Edition: Bedrock Edition: Block data edit | edit source] Main article: Block entity format [NBT Compound / JSON Object] Block entity data

> Tags common to all block entities see Template:Nbt inherit/blockentity/template

> Tags common to all objects that use loot tables to produce items see Template:Nbt inherit/lootable/template

> [NBT Compound / JSON Object] item: The item in the block. May not exist. See item format.

> Steve and Ari excavating suspicious gravel[2]

> Suspicious gravel next to normal gravel

> Thrown Splash Potion Lingering Potion



### Pottery Sherd – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Pottery_Sherd>
- **页面摘要**：Pottery sherds&#91;note 1&#93; are items with 23 variants used to craft decorated pots with ornamental designs. Pottery sherds are found in trial chambers, suspicious sand, and suspicious gravel.

**原文引用：**

> 3 Usage 3.1 Crafting ingredient

> When a decorated pot is broken with a pickaxe, axe, shovel, hoe, sword, mace, or trident that is not enchanted with Silk Touch, it drops all of the pottery sherds and bricks used to craft it. If it is broken with your fist or tools enchanted with Silk Touch the pot itself will drop.

> Pottery sherds can be found as suspicious sand or suspicious gravel loot in trail ruins, ocean ruins, desert pyramids, and desert wells, and can be extracted from these blocks using a brush.

> Decorated pots with scrape, flow, and guster pottery sherds on their sides naturally generate in trial chambers. For a randomly generated pot in trial chambers, there is 1⁄13 chance for each sherd respectively, that a pot has one of these sherds.

> Bedrock Edition edit | edit source] Issues edit | edit source] Issues relating to "Pottery Sherd" are maintained on the bug tracker. Issues should be reported and viewed there. Gallery edit | edit source] Icons edit | edit source] Angler pottery sherd

> Pixel artwork of Ari holding a skull pottery sherd

> Ari holding up an arms up pottery sherd



### Brush – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Brush>
- **页面摘要**：A brush is a tool used in archaeology to excavate suspicious sand and suspicious gravel for different items. Brushes also can be used on armadillos to get armadillo scutes.

**原文引用：**

> 2 Usage 2.1 Brushing 2.1.1 Suspicious blocks

> Using the brush on any block (apart from suspicious blocks) displays a brushing animation, slowing down the player and creating breaking particles, but not actually damaging the block or brush.

> When continuously brushing suspicious sand or suspicious gravel, an item dependent on the structure's loot table slowly emerges from it until it drops out, and the block turns into regular sand or regular gravel, depleting 1 durability point on the brush. It takes 96 game ticks (4.8 seconds) to brush a single suspicious block.

> If the player stops brushing a suspicious block, the block remains in its half-excavated state for a few seconds, before gradually returning to its unexcavated state one stage at a time.

> When using the brush on an armadillo, it drops a single armadillo scute. Brushing an armadillo removes 16 points of durability from the brush. A brush with full durability and no enchantments can brush an armadillo four times in Java Edition or five times in Bedrock Edition before breaking.

> A brush can be combined with another brush in an anvil, preserving the enchantments of both.

> A brush can receive the following enchantments:

> Advancements edit | edit source] History edit | edit source] Development edit | edit source] Java Edition edit | edit source] Bedrock Edition edit | edit source] Issues edit | edit source] Issues relating to "Brush" are maintained on the bug tracker. Issues should be reported and viewed there. Trivia edit | edit source] During animatics for the Trails & Tales trailer, Ari can be seen holding what appears to be the original design of the brush.[1][2]

> Teaser of Alex holding a brush

> Ari building a sandcastle with a brush.

> Tutorial for crafting a brush in Timeless Trails

> Sticker of a brush from 15 Year Journey

> "Taking Inventory: Brush" by Duncan Geere – Minecraft.net, July 6, 2023.



### Archaeology – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Archaeology>
- **页面摘要**：Archaeology is a gameplay mechanic that allows the player to find items representing historical artifacts inside suspicious sand and suspicious gravel.

**原文引用：**

> Archaeology is a gameplay mechanic that allows the player to find items representing historical artifacts inside suspicious sand and suspicious gravel.

> In Java Edition and Bedrock Edition, each trail ruins common suspicious gravel contains 1 item stack, with the following distribution:

> In Java Edition and Bedrock Edition, each cold ocean ruins suspicious gravel contains 1 item stack, with the following distribution:

> In Java Edition and Bedrock Edition, each warm ocean ruins suspicious sand contains 1 item stack, with the following distribution:

> Bedrock Edition edit | edit source] Clay pots.

> Dig site from Minecraft Live 2020.

> Excavation site render from the image.

> Excavation site tent render from the image.

> Excavation site research station render from the image.

> Issues relating to "Archaeology" are maintained on the bug tracker. Issues should be reported and viewed there.

> Two stacked pots outside a desert pyramid.

> A pot next to a dropped brush.

> Four pots inside a desert pyramid.

> Pots stacked next to a desert village house.

> Two lone pots next to a desert well.



### Crying Obsidian – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Crying_Obsidian>
- **页面摘要**：Crying obsidian is a luminous variant of obsidian that can be used to craft respawn anchors. Purple particles drip from its faces. Like obsidian, It has high hardness and blast resistance, making it immune to normal explosions. It can be obtained by mining it with a diamond or netherite pickaxe, and...

**原文引用：**

> Crying obsidian drops itself when it's destroyed.

> Crying obsidian generates as part of some ruined portals. Each obsidian has a 15% chance to generate as crying obsidian.

> Piglins have a ~8.53% chance (40⁄469) to barter 1–3 crying obsidian when given a gold ingot. This is both the most reliable way to obtain crying obsidian, and also the only renewable source of it.

> Much like obsidian, crying obsidian is a resilient building block. It has a blast resistance of 1,200 and cannot be destroyed by the ender dragon. However, crying obsidian cannot be used to create a nether portal frame,[1] and the End crystal is unable to be placed on it.[2]

> When placed, crying obsidian occasionally produces purple dripping particles, which are purely decorative.

> Particles emitted from crying obsidian can pass through certain non-solid blocks, such as glow lichen and sculk veins.

> Crying obsidian gives off a light level of 10, which does not melt snow or ice. Its blast resistance distinguishes it from other light-emitting blocks.

> Crying obsidian cannot be pushed by pistons, and cannot be pulled by sticky pistons.

> Bedrock Edition edit | edit source] Issues edit | edit source] Issues relating to "Crying Obsidian" are maintained on the bug tracker. Issues should be reported and viewed there. Trivia edit | edit source] When it was originally going to be added in Beta 1.3, it was going to act as a way to reset the player’s spawn point and would be crafted using lapis lazuli.[citation needed] When beds were added, they took this role instead. In 1.16, the respawn anchor was added, which is crafted with crying obsidian.

> According to Brandon Pearce, crying obsidian was added when they wanted to have cracked obsidian for the ruined nether portals. They decided to add it as crying obsidian instead because it was more unique and due to high player demand.[citation needed]

> The team considered having crying obsidian be obtained by throwing obsidian through a nether portal, or by having regular obsidian be struck by lightning. However, they chose bartering with piglins as a way to make bartering useful.[8]

> The earliest known instance of a developer referring to the original crying obsidian texture as "crying obsidian"[9] significantly postdates the name's general adoption by the community. The earliest known usages of the name "crying obsidian"[10][11] are from about two months earlier. As it had no given name, it was first referred to as a "mystery block" with crying obsidian being given as one potential name among others, such as "bleeding obsidian".[12][13][14][15]

> A comparison between glowing obsidian (left), crying obsidian (middle), and regular obsidian (right)

> A bunch of crying obsidian placed in the Nether

> Obsidian and crying obsidian, as they appear in the Programmer Art resource pack. Note how it still produces purple particles.



### Eye of Ender – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Eye_of_Ender>
- **页面摘要**：An eye of ender is a craftable item that can be thrown in the Overworld to show the direction of the nearest stronghold, which may break the eye. 12 eyes of ender are required to activate a stronghold's End portal (which may generate with some of the eyes already in place), which leads to the End dimension...

**原文引用：**

> Legacy Console Edition edit | edit source] New Nintendo 3DS Edition edit | edit source] The eye of ender used to appear large in third-person view.

> Issues edit | edit source] Issues relating to "Eye of Ender" are maintained on the bug tracker. Issues should be reported and viewed there. Trivia edit | edit source] When thrown in third-person view, the eyes of ender fly out from the player's chest instead of their hand.

> In Bedrock Edition the eye of ender flies out of the top right of the screen above the player head.

> In Bedrock Edition if the player travels beyond a certain radius (roughly 740,000 blocks), eyes of ender always point to a stronghold near spawn, even though strongholds continue to generate past this limit. If one travels to this limit, they can see eyes of ender suddenly switching direction. A similar phenomenon occurs with the /locate command.

> An End portal frame containing a few eyes of ender.

> An ender chest depicting an eye of ender on the front.

> An enchanted eye of ender obtained with commands being thrown. Eyes of ender retain their components, including name and enchantments, when used.

> Official T-shirt artwork "Eye of Ender" sold by JINX.

> A Halloween T-Shirt design featuring an eye of ender.

> Tyler throwing an eye of ender in Minecraft: Volume 1.

> JSFiddle Eye of Ender triangulator - can guess the location of other 2 strongholds in the first ring

> Minecraft Stronghold Locator Eye of Ender throw plotting visualizer - zoomable to show all possible stronghold rings

> Python Eye of Ender throw plotting tool

> Chunk Base Stronghold Finder (seed-based)

> Thrown Splash Potion Lingering Potion



### Respawn Anchor – Minecraft Wiki
- **来源类型**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Respawn_Anchor>
- **页面摘要**：The respawn anchor is a block that allows the player to set their spawn point in the Nether, provided it's fueled with glowstone blocks.

**原文引用：**

> A respawn anchor drops itself when destroyed, but resets glowstone charges back to 0 when broken.

> While the ingredients to craft a respawn anchor are all native to the Nether, they are also obtainable in the Overworld: glowstone can be obtained from trading with villagers or wandering traders, or crafted from glowstone dust dropped by witches; crying obsidian can be found in ruined portals.

> Like obsidian and crying obsidian, the respawn anchor can't be destroyed by the ender dragon.

> The respawn anchor is used to respawn in the Nether, even if the player leaves the Nether. Once the block is charged, it can be used to set the player's respawn location.

> When crafted, a respawn anchor has no (zero) charge and can't yet be used until charged. Using a glowstone block (not glowstone dust) on it adds a charge. The anchor accepts up to 4 charges, and the charge level is indicated by a dial on the side of the block.

> The first charge makes the respawn anchor glow with a light level of 3. Each glowstone after the first increases the light level by 4, up to a maximum of 15.

> To set the player's spawn location to the respawn anchor they must use it, just like one does with a bed. The anchor must at least have one charge, and it must be in the Nether. A confirmation appears when the player's respawn location is set. Other players can also set their spawn point to the same respawn anchor. Each respawn uses up one charge, even if used by another player.

> Using a charged anchor overrides any other spawn location the player might have had, as with a bed. The respawn anchor does not serve as a backup spawn point to a missing or obstructed bed.

> Upon death, the player respawns next to the anchor, and it loses one charge. If a player's respawn anchor is destroyed, if its charges have been exhausted, or if the area around it is made unsuitable for respawning, a message appears saying "You have no home bed or charged Respawn Anchor, or it was obstructed"‌[Java Edition only] or "Your respawn anchor was out of charges, missing, or obstructed"‌[Bedrock Edition only], and the player respawns at the world spawn point. Returning through an End portal is not considered a respawn, and does not use any charges.

> A respawn anchor can be shared among several players. When shared, remaining charges are shared as well. In Hardcore mode, the respawn anchor does not resurrect the player, but may still teleport them and consume charges.

> If the player attempts to set their spawn at a charged respawn anchor in the Overworld, the End, or custom dimensions in which they are disabled, the block explodes (and is destroyed) similar to when a bed is used in the Nether or the End. The explosion has a power of 5 and sets fire to surrounding blocks.

> Upon death from a respawn anchor explosion, the message "(Player) was killed by [Intentional Game Design]" appears. In Bedrock Edition, respawn anchor explosions can be disabled by setting the gamerule respawnBlocksExplode to false which can be done with the following command: /gamerule respawnBlocksExplode; this still does not permit respawn anchors to be used in invalid dimensions.

> When charged, a redstone comparator gives a signal depending on the number of charges: 3 for one charge, 7 for two charges, 11 for three charges, 15 for four charges. An empty anchor gives a signal of 0.

> The respawn anchor can also be charged with a dispenser containing glowstone.

> Hoglins flee from respawn anchors, even when uncharged.



---


**本文件统计**：16 个来源 · 见原文段落如上

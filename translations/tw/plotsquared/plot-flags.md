<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8a32479c1acadf3eb085df63adedc55a",
  "translation_date": "2025-05-13T03:46:06+00:00",
  "source_file": "plotsquared/plot-flags.md",
  "language_code": "tw"
}
-->
# Plot flags

## 介紹

這個完整的旗標系統讓你可以做各種設定，例如調整地皮的天氣。

設定旗標很簡單，只要使用 `/plot flag set <flag> <value>`。布林旗標的值則是 'true' 或 'false'。

## 旗標列表

要顯示旗標列表，使用 `/plot flag list`。這些值是可點擊的，點擊旗標名稱會顯示該旗標的相關資訊。如果你已經知道旗標名稱，也可以直接使用 `/plot flag info <flag>`。

![Flag system](https://i.imgur.com/uTPjJEE.png)

## 預設地皮和道路旗標

你可以在 `plugins/PlotSquared/config/worlds.yml` 為每個世界設定預設旗標。預設旗標會出現在每個已認領的地皮，除非該地皮手動設定了不同的值。

以下是一個**範例**，設定 `use` 旗標以允許與門、活板門、拉桿、柵欄、壓力板、按鈕和陷阱線互動：

```yaml
worlds:
  <world>:
    [...]
    flags:
      use: "oak_door,iron_trapdoor,lever,acacia_fence_gate,light_weighted_pressure_plate,oak_button,tripwire"
      pvp: true
```

_`<world>` 表示該地皮世界的名稱。_

你也可以使用 [Vanilla block tags](vanilla-tags.md)。

道路旗標的設定方式相同。

**範例：**

```yaml
worlds:
  <world>:
    [...]
    road:
      [...]
      flags:
        use: "oak_door,iron_trapdoor,lever,acacia_fence_gate,light_weighted_pressure_plate,oak_button,tripwire"
        pvp: true
```

_`<world>` indicates the name of that plotworld._

## Flag types

### BlockTypeList

A list of blocks, supporting both legacy numerical IDs and new string IDs e.g.

* `grass_block` for grass blocks
* `7` for bedrock
* `7,3` for bedrock and dirt
* `35:14,35:15` for red and black wool

These flags also support [vanilla-tags](vanilla-tags.md), like:

* `#signs` for all sign types
* `#buttons` for all button types

### Boolean

Accepts `true` or `false`.

### Double

Accepts any decimal number (all real numbers).

### Enum

Accepts a predefined collection of values.

### Integer

Accepts all integers.

### Internal

Flags used internally.

### Miscellaneous

Accept commands with multiple parameters, e.g `/gamemode creative`.

### String

Accept flags with multiple string parameters, e.g. `/plot f set greeting Welcome to my plot!`

### TeleportDeny

Accepts the follow plot membership `trusted`, `members`, `nonmembers`, `nontrusted` and `nonowners`.

### Timed

A binary tuple of numbers e.g. `53 6` or `7 93`.

## Flag Permissions

### Basic Permission Schema

To give a player access to a flag, you need to assign the following permissions, and exchange the value if wanted:

* `plots.set.flag`
* `plots.flag`
* `plots.flag.add`
* `plots.flag.remove`

{% hint style="info" %}
Also, you can assign [`plots.permpack.basicflags`](permission/permission-packs.md#plotspermpackbasicflags) to cover the following permissions and lots of the basic flags.
{% endhint %}

### Flag specific permission

`plots.set.flag.<name>.*` (e.g. `plots.set.flag.fly.*`)
The asterisk covers the values of the flag, if it's a boolean flag you cover `true` and `false`, if it's a Long flag you cover all positive numbers and so on. Make sure to decide whether you need it or not.

## Terminology

The following tables contain phrases covering certain stances of plot member inheritance and flag states. We will explain the phrases used below.

* Player: The player, as in user of the server.
* Guest: Person who is not added to the plot [tiers](plot-membership-tiers.md).
* False: The flag intended behavior is not enabled by default.
* True: The flag intended behavior is enabled by default.
* None: The flag intended behavior is not set by default.
* Infinity: The flag is not bound to an amount and allows infinite types of the flag.
* Null: The flag intended behavior cannot be set outside of the API.
* Empty: The flag variable is empty and won't appear to the user.
* Not Buyable: The flag variable is not set, therefore the plot is not buyable.
* Disabled: The flag variable is not set, therefore the intended behavior is not defined.

## Entity Categories

Flags such as mob caps, interaction flags, etc, make use of entity categories. PlotSquared divides entities in the following categories:

* **animal:** cod donkey squid skeleton_horse mule trader_llama parrot zombie_horse cow horse bee polar_bear pufferfish cat bat salmon fox pig llama iron_golem turtle tropical_fish sheep snow_golem mooshroom ocelot dolphin chicken wolf panda rabbit
* **hostile:** blaze pillager skeleton giant elder_guardian zombie_pigman end_crystal ravager ghast guardian vindicator magma_cube spider creeper wither evoker slime illusioner phantom witch wither_skeleton husk ender_dragon cave_spider stray enderman silverfish endermite vex zombie drowned zombie_villager, shulker
* **player:** player
* **projectile:** ender_pearl dragon_fireball fireball wither_skull llama_spit fishing_bobber experience_bottle egg arrow small_fireball
* **vehicle:** spawner_minecart donkey pig llama furnace_minecart skeleton_horse mule hopper_minecart trader_llama zombie_horse tnt_minecart boat chest_minecart horse command_block_minecart minecart
* **villager:** villager wandering_trader
snowball spectral_arrow shulker_bullet potion trident
* **hanging:** item_frame leash_knot painting
* **other:** dragon_fireball tnt experience_orb lightning_bolt fireball wither_skull area_effect_cloud evoker_fangs eye_of_ender armor_stand small_fireball firework_rocket falling_block item
* **tamable:** cat trader_llama parrot zombie_horse donkey wolf llama horse skeleton_horse mule

## Flags

### BlockTypeList

| Name  | Description                                                                                                             | Default Value |
|-------|-------------------------------------------------------------------------------------------------------------------------|---------------|
| break | Define a list of materials players should be able to break in the plot even when they aren’t added to the plot.         | None          |
| place | Define a list of materials players should be able to place in the plot even when they aren’t added to the plot.         | None          |
| use   | Define a list of materials players should be able to interact with in the plot even when they aren’t added to the plot. | None          |

### Boolean

| Name                    | Description                                                                                                                | Default Value |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------|---------------|
| animal-attack           | Set to `true` to allow animals to be attacked in the plot.                                                                 | False         |
| animal-interact         | Set to `true` to allow animals to be interacted with in the plot.                                                          | False         |
| beacon-effects          | Set to `false` to disable beacon effects on the plot.                                                                      | True          |
| block-burn              | Set to `true` to allow blocks to burn within the plot.                                                                     | False         |
| block-ignition          | Set to `false` to disallow blocks to ignite within the plot.                                                               | True          |
| chat                    | Set to `false` to prevent plot chat on the plot.                                                                           | False         |
| concrete-harden         | Set to `false` to disable concrete powder forming to concrete with water.                                                  | True          |
| coral-dry               | Set to `true` to allow corals to dry within the plot.                                                                      | False         |
| crop-grow               | Set to `false` to disable crop growing on the plot.                                                                        | True          |
| copper-oxide            | Set to `true` to allow copper to oxide within the plot.                                                                    | False         |
| deny-exit               | Set to `true` to disallow players from exiting the plot.                                                                   | False         |
| deny-portal-travel      | Prevents players from travelling across dimensions by using portals.                                                       | False         |
| deny-portals            | Prevents players from creating portals of any kind.                                                                        | False         |
| device-interact         | Set to `true` to allow devices to be interacted with in the plot.                                                          | False         |
| disable-physics         | Set to `true` to disable block physics in the plot.                                                                        | False         |
| drop-protection         | Set to `true` to prevent dropped items from being picked up by non-members of the plot.                                    | False         |
| edit-sign               | Set to `true` to allow players to edit signs in the plot or on the road.                                                   | False         |
| entity-change-block     | Set to `true` to allow entities to change blocks within the plot, if not covered by other flags.                           | False         |
| explosion               | Set to `true` to allow explosions inside a plot.                                                                           | False         |
| fishing                 | Set to `true` to allow guests to use a fishing rod in the plot.                                                            | False         |
| fly                     | Set to `true` to enable flight within the plot.                                                                            | False         |
| forcefield              | Set to `true` to enable member forcefield in the plot.                                                                     | False         |
| grass-grow              | Set to `false` to disable grass to grow within the plot.                                                                   | True          |
| hanging-break           | Set to `true` to allow guests to break hanging objects in the plot. Applies to the following entity categories: hanging    | False         |
| hanging-place           | Set to `true` to allow guests to hang objects in the plot.                                                                 | False         |
| hide-info               | Set to `true` to hide plot information.                                                                                    | False         |
| hostile-attack          | Set to `true` to enable players to attack hostile mobs in the plot.                                                        | False         |
| hostile-interact        | Set to `true` to allow players to interact with hostile mobs in the plot.                                                  | False         |
| ice-form                | Set to `true` to allow ice to form in the plot.                                                                            | False         |
| ice-melt                | Set to `true` to allow ice to melt in the plot.                                                                            | False         |
| instabreak              | Set to `true` to allow blocks to be instantaneously broken in survival mode.                                               | False         |
| invincible              | Set to `true` to prevent players from taking damage inside the plot.                                                       | False         |
| item-drop               | Set to `false` to prevent items from being dropped inside the plot.                                                        | True          |
| keep-inventory          | Prevents players from dropping their items when they die inside the plot.                                                  | False         |
| kelp-grow               | Set to `false` to disable kelp to grow in the plot.                                                                        | True          |
| leaf-decay              | Set to `false` to prevent leaves from decaying.                                                                            | True          |
| lectern-read-book       | Prevent players taking books from lecterns.                                                                                | False         |
| misc-break              | Set to `true` to allow guests to break miscellaneous items. Applies to the following entity categories: armorstands        | False         |
| misc-place              | Set to `true` to allow guests to place miscellaneous items.                                                                | False         |
| misc-interact           | Set to `true` to allow guests to interact with miscellaneous items. Applies to the following entities                      |               |
| mob-break               | Set to `true` to allow mobs to break blocks within the plot.                                                               | False         |
| mob-place               | Set to `true` to allow mobs to place blocks within the plot.                                                               | False         |
| mycel-grow              | Set to `false` to disable mycelium to grow in the plot.                                                                    | True          |
| no-worldedit            | Set to `true` to disable (FastAsync)WorldEdit usage within the plot.                                                       | False         |
| notify-enter            | Set to `true` to notify the plot owners when someone enters the plot.                                                      | False         |
| notify-leave            | Set to `true` to notify the plot owners when someone leaves the plot.                                                      | False         |
| player-interact         | Set to `true` to allow guests to interact with players in the plot.                                                        | False         |
| pve                     | Set to `true` to enable PVE inside the plot.                                                                               | False         |
| pvp                     | Set to `true` to enable PVP inside the plot.                                                                               | False         |
| prevent-creative-copy   | Prevents people from copying item NBT data in the plot unless they're added as members.                                    | False         |
| projectiles             | Prevents guests from shooting projectiles on the plot when set to false.                                                   | False         |
| projectile-change-block | Set to `true` to allow projectiles to change blocks (tnt, etc.) on the plot.                                               | False         |
| redstone                | Set to `false` to disable redstone in the plot.                                                                            | True          |
| server-plot             | Set to `true` to turn the plot into a server plot. This is equivalent to setting the server as the plot owner.             | False         |
| snow-form               | Set to `false` to disallow snow to form within the plot.                                                                   | False         |
| snow-melt               | Set to `true` to allow snow to melt within the plot.                                                                       | True          |
| soil-dry                | Set to `true` to allow soil to dry within the plot.                                                                        | False         |
| tamed-attack            | Set to `true` to allow guests to attack tamed animals in the plot.                                                         | False         |
| tamed-interact          | Set to `true` to allow guests to interact with tamed animals in the plot.                                                  | False         |
| tile-drop               | Set to `false` to prevent blocks from dropping items in the plot.                                                          | True          |
| untrusted-visit         | Set to `false` to disallow untrusted players from visiting the plot.                                                       | True          |
| vehicle-break           | Set to `true` to allow guests to break vehicles in the plot.                                                               | False         |
| vehicle-place           | Set to `true` to allow guests to place vehicles in the plot.                                                               | False         |
| vehicle-use             | Set to `true` to allow guests to use vehicles in the plot. Applies to the following entity categories: vehicle             | False         |
| villager-interact       | Set to `true` to allow guests to interact with villagers in the plot.                                                      | False         |
| vine-grow               | Set to `false` to disable vines to grow within the plot.                                                                   | True          |
| weaving-death-place     | Set to `true` to allow the spawning of cobwebs on death by the [Weaving status effect](https://minecraft.wiki/w/Weaving).  | False         |

### Double

| Name  | Description                                                                                                                               | Default Value |
|-------|-------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| price | If set a plot can be bought for this price using `/plot buy`. Requires economy to be enabled and lists plots under `/plots list forsale`. | Not Buyable   |

### Enum

| Name          | Description                                                                                                              | Default Value |
|---------------|--------------------------------------------------------------------------------------------------------------------------|---------------|
| deny-teleport | Deny a certain group from teleporting to the plot. Available groups: members, nonmembers, trusted, nontrusted, nonowners | None          |
| liquid-flow   | Set to `false` to disable liquid flowing.                                                                                | None          |
| titles        | Set to `true` to allow the plot title when someone enters the plot.                                                      | None          |
| weather       | Specifies the simulated weather inside the plot. This has no effect of weather-dependent game mechanics.                 | None          |

### Integer

| Name        | Description                                                                                                                                               | Default Value |
|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| animal-cap  | Set to an integer value to limit the amount of animals on the plot. Applies to the following entity categories: animal, villager, tamable                 | Infinity      |
| entity-cap  | Set to an integer value to limit the amount of entities on the plot.                                                                                      | Infinity      |
| hostile-cap | Set to an integer value to limit the amount of hostile entities on the plot. Applies to the following entity categories: hostile                          | Infinity      |
| misc-cap    | Set to an integer value to limit the amount of miscellaneous entities on the plot. Applies to the following entity categories: projectile, other, hanging | Infinity      |
| mob-cap     | Set to an integer value to limit the amount of mobs on the plot. Applies to the following entity categories: animal, villager, tamable, hostile           | Infinity      |
| vehicle-cap | Set to an integer value to limit the amount of vehicles on the plot. Applies to the following entity categories: vehicle                                  | Infinity      |
| time        | Specifies the simulated time inside the plot. This has no effect of time dependent game mechanics.                                                        | Disabled      |

### Internal

| Name     | Description                          | Default Value |
|----------|--------------------------------------|---------------|
| analysis | A multi purpose debug analysis flag. | Null          |
| done     | Mark a plot as done.                 | Null          |

### Miscellaneous

| Name           | Description                                                | Default Value |
|----------------|------------------------------------------------------------|---------------|
| blocked-cmds   | A list of commands that are blocked in the plot.           | None          |
| gamemode       | Determines the gamemode in the plot.                       | None          |
| guest-gamemode | Determines the guest gamemode in the plot.                 | None          |
| music          | Set to a music disk ID (item name) to play the music disc. | None          |

### String

| Name        | Description                                                                                        | Default Value |
|-------------|----------------------------------------------------------------------------------------------------|---------------|
| description | Plot description.                                                                                  | None          |
| farewell    | Message sent to players when leaving the plot.                                                     | None          |
| greeting    | Message sent to players on plot entry.                                                             | None          |
| plot-title  | Set the pop-up title's title and subtitle. Format: `/plot flag set title "A title" "The subtitle"` | 無          |

### 計時型

| 名稱 | 說明                                                                                                                                    | 預設值       |
|------|-----------------------------------------------------------------------------------------------------------------------------------------|-------------|
| feed | 指定間隔秒數及可選的餵食量（預設為0，即原版自然回復）。                                                                                 | 無          |
| heal | 指定間隔秒數及可選的治療量（預設為0，即原版自然回復）。                                                                                 | 無          |

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於提供準確的翻譯，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議使用專業人工翻譯。我們不對因使用本翻譯而產生的任何誤解或誤譯負責。
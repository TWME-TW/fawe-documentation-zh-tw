<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "22175baad3ba3a37ce6d80a341b294a0",
  "translation_date": "2025-05-13T03:57:49+00:00",
  "source_file": "plotsquared/configuration/worlds.md",
  "language_code": "tw"
}
-->
# 世界設定

## 介紹

此檔案包含每個世界的設定。如果你使用 plot-setup `/plot setup`，檔案輸入會根據你的設定參數由外掛自動產生。否則你必須手動更改預設值。

{% hint style="tip" %}
關於區塊桶的更多資訊，請參考[這頁](../block-bucket.md)。
{% endhint %}

*位置於：* `/plugins/PlotSquared/config/worlds.yml`

## 預設

```yaml
configuration_version: v5
worlds:
  # The name of the world
  plotworld:
    plot:
      # The road height above from Y 0
      height: 62
      # The plot biome
      biome: minecraft:forest
      # The material to use for the plot signs
      sign_material: OAK_WALL_SIGN
      # The road length around a plot
      size: 42
      # Uses the block bucket format:
      # ex: stone,grass_block
      filling: minecraft:stone
      # Whether plots should be merged
      auto_merge: false
      # Whether the plot should have a bedrock layer at the bottom
      bedrock: true
      # Whether signs should be created at the corner of a plot
      create_signs: true
      # Uses the block bucket format:
      # ex: stone,grass_block
      floor: minecraft:grass_block
    # Configure the wall
    wall:
      # Uses the block bucket format:
      # ex: stone,grass_block
      filling: minecraft:stone
      # Uses the block bucket format:
      # ex: stone,grass_block
      block_claimed: minecraft:sandstone_slab
      height: 62
      # Uses the block bucket format:
      # ex: stone,grass_block
      block: minecraft:stone_slab
      # Whether blocks should be placed on top of the border
      place_top_block: true
    misc_spawn_unowned: false
    # Configure the road
    road:
      # Uses the block bucket format:
      # ex: stone,grass_block
      block: minecraft:quartz_block
      # Apply flags for the road within the following pattern:
      # flags:
      #	  pvp: true
      #		gamemode: survival
      # Do NOT add them inside the brackets
      flags: {}
      # Road height from Y 0
      height: 62
      # Road width along a side of a plot
      width: 7
    # Configure the home
    home:
      # side, center/middle or x,z (relative to the plot) or x,y,z
      nonmembers: side
      # side, center/middle or x,z (relative to the plot) or x,y,z
      default: side
    # Schematic generating / auto pasting
    schematic:
      # Whether the user can choose between a schematic when they claim a plot
      specify_on_claim: false
      # Whether the schematic should be pasted on claim
      on_claim: false
      # Define the schematic within the following format:
      # file:
      #		example.schem
      file: 'null'
      schematics: []
    # Default plot chat mode (toggled with `/plot toggle chat`)
    chat:
      # Whether plotchat will be on always
      forced: false
      enabled: true
    # Command costs
    economy:
      # Can use ANTLR's lexer tokens for dynamic prices
      # See https://worldedit.enginehub.org/en/latest/usage/other/expressions/
      # for a list of supported arguments. The plot variable is referenced as plots
      prices:
        merge: 100
        sell: 100
        claim: 100
      # Whether the setting should be active
      use: false
    world:
      # Max world generation height (Y)
      max_gen_height: 319
      # Max build height (Y)
      max_height: 320
      gamemode: creative
      # Used for the gamemode flag
      # Min world generation height (Y)
      min_gen_height: -64
      # Min build height (Y)
      min_height: -63
      # World border expands dynamically (false = disabled)
      border: false
      # plot offset for the world-border around the claimed plots
      border_size: 1
    event:
      spawn:
        # Whether spawn eggs are enabled
        egg: false
        # Whether breeding is enabled
        breeding: false
        # Whether custom events are enabled
        custom: true
    # Whether natural mob spawning is enabled
    natural_mob_spawning: false
    # Whether spawners are spawning mobs
    mob_spawner_spawning: false
    # Global plot flags, see: https://intellectualsites.github.io/plotsquared-documentation/plot-flags
    flags: {}
```

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於翻譯的準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤釋負責。
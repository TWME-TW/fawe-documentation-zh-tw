<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "955d878e57b557823a93b942ea9770cb",
  "translation_date": "2025-05-13T03:56:02+00:00",
  "source_file": "fastasyncworldedit/commands/selection/selection.md",
  "language_code": "tw"
}
-->
# Selection Commands

## Sel

有些 FAWE 指令需要選取區域來指定要修改的範圍。這個指令讓你可以修改或取消目前的選取。

**用法:** `//sel [-d] [selector]`

- 不帶參數會取消目前的區域選取。
- `selector` 參數用來改變選取的形狀（= 選取類型）。
- 使用 `-d` 可以更改預設的選取類型。

**別名:** `[ deselect, desel, /; ]`

**權限:** `worldedit.analysis.sel`

### 選取類型

#### Cuboid

這是最常用的選取方式，也是**預設類型**。Cuboid 選取需要定義兩個點。

![Selection Type 1](../../../../../fastasyncworldedit/commands/selection/images/sel-cuboid.png)

#### Extend

這是 Cuboid 選取的進階版本。定義前兩點後，可以透過更多點來擴展選取範圍，最後的選取仍然是 Cuboid。

![Selection Type 2](../../../../../fastasyncworldedit/commands/selection/images/sel-extend.png)

#### Poly

這種類型會產生一個多邊形的選取範圍，邊界是自由多邊形。多邊形的高度由最高與最低點的 Y 座標決定。可以定義無限多點，邊界會連接所有角落，並依序編號。

![Selection Type 2](../../../../../fastasyncworldedit/commands/selection/images/sel-poly.png)

#### Ellipsoid

此選取範圍是橢球體。`position 1` 參數定義中心點，`position 2` 參數用來調整橢球的長度、寬度和高度。

![Selection Type 2](../../../../../fastasyncworldedit/commands/selection/images/sel-ellipsoid.png)

#### Sphere

此選取範圍是球形。`position 1` 參數定義中心點，`position 2` 參數定義半徑。

![Selection Type 2](../../../../../fastasyncworldedit/commands/selection/images/sel-sphere.png)

#### Cyl

此選取類型會產生圓柱體選取。`position 1` 參數定義圓柱中心點，`position 2` 參數定義半徑與深度（高度）。只能做垂直的圓柱體。

![Selection Type 2](../../../../../fastasyncworldedit/commands/selection/images/sel-cyl.png)

#### Polyhedron

別名: "Convex" 和 "Hull"

這種類型是自由多面體選取。與 `poly` 選取不同，這裡不會決定高度。

#### Fuzzy

別名: "Magic"

這種類型會選取與你點擊的方塊相同材質的所有方塊。舉例來說，點擊一個 `orange_wool` 方塊，附近所有相鄰的 `orange_wool` 方塊都會被選取。

- 用左鍵點擊選擇第一個方塊／材質，接著用右鍵點擊可以加入更多選擇。
- 它會用路徑搜尋檢查鄰近方塊（上下、側邊的方塊分別檢查），所以不需要半徑參數。

## Wand

使用此指令可以獲得 FAWE 的 [工具物品](../../tool-items/tool-items.md)。

**用法:** `//wand [-n]`

- 會先取得 [Wand 工具物品](../../tool-items/tool-items.md#wand-tool-item)。
- 使用 `-n` 參數則會同時取得 [Navigation 工具物品](../../tool-items/tool-items.md#navigation-tool-item)。

**權限:** `worldedit.wand`

## Pos1 和 Pos2

另一種定義選取角落的方法是使用 `//pos` 指令。若無指定參數，位置會設為你目前站立的座標（如圖）。也可以用 `coordinates` 參數明確指定座標。參數語法為 `<X>,<Y>,<Z>` 或 `<one value for X, Y and Z>`。

**用法:** `//pos1 [coordinates]` 和 `//pos2 [coordinates]`

**別名:** `//1` 和 `//2`

**權限:** `worldedit.selection.pos`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/selection/images/pos.png)

## Hpos1 和 Hpos2

這是第三種定義選取角落的方法。會選取你[準心](https://minecraft.wiki/w/File:HUD_example.png)下一個實體方塊。

**用法:** `//hpos1` 和 `//hpos2`

**權限:** `worldedit.selection.hpos`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/selection/images/hpos.png)

## Chunk

此指令會將選取類型改成 `cuboid`，並選取指定 [chunk](https://minecraft.wiki/w/Chunk) 中的所有方塊。

**用法:**

`//chunk [-cs] [coordinates]`

- 不帶參數會選取你目前所在的 chunk。
- 目標 chunk 可用方塊的 `x`、`y` 和 `z` 座標明確指定。
- 或是使用有效的 [chunk 座標](https://minecraft.wiki/w/Chunk#Finding_chunk_edges) 並搭配 `-c` 標記。
- `-s` 標記可以重新選取你目前選取範圍的所有 chunk，這種情況不需指定座標。

**權限:** `worldedit.selection.chunk`

## Shift

使用 shift 指令可以移動你的選取範圍。與 `//move` 指令不同的是，這裡不是移動所有方塊（見圖）。

**用法:**

_主要用法:_

`//shift <amount>`

- 使用 `amount` 參數指定移動的方塊數量。
- 負值的 `amount` 會反轉移動方向。

_次要用法:_

`//shift <amount> [direction]`

- 要指定目標方向，可以看向該方向或使用 `direction` 參數。

{% hint style="tip" %}
有效方向參數清單請參考 [這裡](../commands.md#direction-argument)。
{% endhint %}

**權限:** `worldedit.selection.shift`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/selection/images/shift.png)

## Inset

此指令會縮小你的選取範圍。

**用法:**

_主要用法:_

`//inset <amount>`

- 不帶任何標記，會同時從所有邊縮小相同的距離（見圖）。

_次要用法:_

`//inset [-hv] <amount>`

縮小距離也可以明確指定：
- 水平方向的縮小距離用 `amount` 搭配 `-h` 標記。
- 垂直方向的縮小距離用 `amount` 搭配 `-v` 標記。

**權限:** `worldedit.selection.inset`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/selection/images/inset.png)

## Outset

此指令會放大你的選取範圍。

**用法:**

_主要用法:_

`//outset <amount>`

- 不帶任何標記，會同時從所有邊放大相同的距離（見圖）。

_次要用法:_

`//outset [-hv] <amount>`

放大距離也可以明確指定：
- 水平方向的放大距離用 `amount` 搭配 `-h` 標記。
- 垂直方向的放大距離用 `amount` 搭配 `-v` 標記。

**權限:** `worldedit.selection.outset`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/selection/images/outset.png)

## Contract

類似 `inset` 指令，可以縮小選取範圍，但這裡是針對指定方向進行縮小，只會對一或兩邊生效（見圖）。

**用法:**

_主要用法:_

`//contract <amount> [direction]`

- 使用 `amount` 參數指定縮小的方塊數量。
- 指定目標方向，可以看向該方向或使用 `direction` 參數。

{% hint style="tip" %}
有效方向參數清單請參考 [這裡](../commands.md#direction-argument)。
{% endhint %}

_次要用法:_

`//contract <amount> <reverse-amount> [direction]`

- 第二個 `reverse-amount` 會對相反方向的邊放大選取範圍。

**權限:** `worldedit.selection.contract`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/selection/images/contract.png)

## Expand

類似 `outset` 指令，可以放大選取範圍，但這裡是針對指定方向進行放大，只會對一或兩邊生效（見圖）。

**用法:**

_主要用法:_

`//expand <amount> [direction]`

- 使用 `amount or "vert"` 參數指定放大的方塊數量。
- 指定目標方向，可以看向該方向或使用 `direction` 參數。
- 使用最簡短的 expand 指令 `vert`，選取會在世界的垂直線方向全部放大。

{% hint style="tip" %}
有效方向參數清單請參考 [這裡](../commands.md#direction-argument)。
{% endhint %}

_次要用法:_

`//expand <amount or "vert"> <reverse-amount> [direction]`

- 第二個 `reverse-amount` 會對相反方向的邊縮小選取範圍。

**權限:** `worldedit.selection.expand`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/selection/images/expand.png)

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於準確性，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所引起之任何誤解或誤譯負責。
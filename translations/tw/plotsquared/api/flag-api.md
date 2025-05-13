<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "6d15a05506602edc4270ccb5c071a3f3",
  "translation_date": "2025-05-13T03:57:18+00:00",
  "source_file": "plotsquared/api/flag-api.md",
  "language_code": "tw"
}
-->
# API Flag 文件說明

## 介紹

plot flag 是可以指定給地塊的屬性，會以某種方式改變它的功能。大部分都可以讓使用者在遊戲中或透過設定檔（針對地塊區域）來指定。

要建立新的 flag，只要繼承 PlotFlag 或其中一個預設類型：

### Flag 類型：
* [BlockTypeListFlag](https://intellectualsites.github.io/plotsquared-javadocs/core/com/plotsquared/core/plot/flag/types/BlockTypeListFlag.html)（儲存 WorldEdit BlockTypes）
* [BlockTypeWrapper](https://intellectualsites.github.io/plotsquared-javadocs/core/com/plotsquared/core/plot/flag/types/BlockTypeWrapper.html)
* [BooleanFlag](https://intellectualsites.github.io/plotsquared-javadocs/core/com/plotsquared/core/plot/flag/types/BooleanFlag.html)
* [DoubleFlag](https://intellectualsites.github.io/plotsquared-javadocs/core/com/plotsquared/core/plot/flag/types/DoubleFlag.html)
* [IntegerFlag](https://intellectualsites.github.io/plotsquared-javadocs/core/com/plotsquared/core/plot/flag/types/IntegerFlag.html)
* [ListFlag](https://intellectualsites.github.io/plotsquared-javadocs/core/com/plotsquared/core/plot/flag/types/ListFlag.html)
* [LongFlag](https://intellectualsites.github.io/plotsquared-javadocs/core/com/plotsquared/core/plot/flag/types/LongFlag.html)
* [NonNegativeIntegerFlag](https://intellectualsites.github.io/plotsquared-javadocs/core/com/plotsquared/core/plot/flag/types/NonNegativeIntegerFlag.html)
* [NumberFlag](https://intellectualsites.github.io/plotsquared-javadocs/core/com/plotsquared/core/plot/flag/types/NumberFlag.html)
* [StringFlag](https://intellectualsites.github.io/plotsquared-javadocs/core/com/plotsquared/core/plot/flag/types/StringFlag.html)
* [TimedFlag](https://intellectualsites.github.io/plotsquared-javadocs/core/com/plotsquared/core/plot/flag/types/TimedFlag.html)

Flags 本質上是不可變的值容器。flag 的值必須能從字串解析出來，並且之後能序列化回字串。

## 查詢 flag 狀態

如果想知道某個地塊上 flag 的目前值，可以直接寫

```java
boolean pvp = plot.getFlag(PvpFlag.class);
```

這個範例中，我們查詢 PvpFlag（BooleanFlag）的狀態，這個方法會直接回傳我們後續想使用的值。

## 建立 flag

每個 flag 包含一個不可變的值。這個值的型別會以泛型參數提供給 PlotFlag 類別，如下：

```java
import com.plotsquared.core.plot.flag.FlagParseException;
import com.plotsquared.core.plot.flag.PlotFlag;

public class YourFlag extends PlotFlag<YourValueType, YourFlag> {
// Your code
}
```

這個 flag 可以實作 `com.plotsquared.core.plot.flag.InternalFlag`, in which case the flag won't be visible to the user. This allows you to store information that is associated with the plot, using the flag framework.

The PlotFlag constructor requires three parameters:

* The (non-null) immutable flag value
* A flag category
* A flag description

The category and description should be a TranslatableCaption `com.plotsquared.core.configuration.caption.TranslatableCaption`.
An instance of Caption can be created by using `com.plotsquared.core.configuration.caption.StaticCaption`。

你的 flag 建構子大致上應該長這樣：

```java
public YourFlag(final YourValueType value) {
  super(value, TranslatableCaption.of("flags.your_flag"), TranslatableCaption.of("flags.your_description"));
}
```

你的 flag 類別需要覆寫以下方法：

* `YourFlag parse(@NotNull String input) throws FlagParseException`
* `YourFlag merge(@NotNull YourValueType newValue)`
* `String toString()`: Returns the string serialization of the current value.
* `String getExample()`: Returns an example argument.
* `YourFlag flagOf(@NotNull YourValueType value)`: Returns a new instance of your flag.

The `parse(String input)` method parses a string input, and returns a new flag instance.
If the input is not valid, `FlagParseException` 會被丟出。它應該長得像這樣：

```java
@Override
public YourFlag parse(@NotNull final String input) throws FlagParseException {
  if (isValid(input)) {
    YourValueType type = convertSomehow(input);
    return flagOf(type);
  }
  throw new FlagParseException(this, input, TranslatableCaption.of("flags.caption_message"));
}
```

caption 的建立方式跟建構子相同。message_en.json 裡面有一些預先做好的錯誤 caption，前綴為 `lags.flag_error_`. The FlagParseException takes in further parameters that will replace the placeholder values in the caption (`+<{value}>+`), if needed.

{% hint style="warning" %}
This method should *NEVER* return null. If the value cannot be parsed, throw an exception.
{% endhint %}

The merge method allows you to merge two different flag instances, which allows users to use the `/plot flag add <flag> <value>` command on the flag. If merging isn't supported, simply return `flagOf(newValue)`.

As the values are immutable, it is possible (and encouraged) to re-use flag instances.

For examples, see: https://github.com/IntellectualSites/PlotSquared/tree/main/Core/src/main/java/com/plotsquared/core/plot/flag/implementations

## Registering a flag

All flags must be registered in the `GlobalFlagContainer`, or else they will not be usable in-game.
Each flag will be applied to every plot, so it is necessary to pick appropriate default flag values.

To register a flag, use:
`com.plotsquared.plot.flags.GlobalFlagContainer().getInstance().addFlag(flagInstance)`

## Adding a flag to a plot

To add a flag to a plot, use `plot.setFlag(flagInstance)`. If you need a new flag instance, and only have the flag type, it is possible to add a flag using `plot.addFlag(GlobalFlagContainer.getInstance().getFlag(flagInstance).createFlagInstance(flagValue))`

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們努力追求準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤譯負責。
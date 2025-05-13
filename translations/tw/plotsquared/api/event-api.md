<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "b94e685e017357907db616afb51df9bc",
  "translation_date": "2025-05-13T03:57:08+00:00",
  "source_file": "plotsquared/api/event-api.md",
  "language_code": "tw"
}
-->
# Event API

## 介紹

PlotSquared 使用 [Guava EventBus](https://github.com/google/guava/wiki/EventBusExplained) 來註冊監聽器並派發事件。

## 事件列表

請查看 [PlotSquared events](https://intellectualsites.github.io/plotsquared-javadocs/core/com/plotsquared/core/events/package-summary.html) 的 Javadoc。

## 取得實例

```java
import org.bukkit.Bukkit;
import org.bukkit.plugin.java.JavaPlugin;

public class MyPlotPlugin extends JavaPlugin {
    public static MyPlotPlugin THIS;

    @Override
    public void onEnable() {
        MyPlotPlugin.THIS = this;
        if (Bukkit.getPluginManager().getPlugin("PlotSquared") != null) {
        // Do something
       }
    }
}
```

## 註冊監聽器

註冊監聽器非常簡單。加上 `@Subscribe` (from the `com.google.common.eventbus` package) annotation to any methods that are listening to events, register the class with the EventBus through `PlotAPI#registerListener(Class)` 就完成了！範例如下：

```java
public class P2Listener {

  // if you like the dependency-injection-like approach:
  public P2Listener(PlotAPI api) {
    api.registerListener(this);
  }

  // less OOP, but if you want to make things easy:
  public P2Listener() {
    PlotAPI api = new PlotAPI();
    api.registerListener(this);
  }

  // A method handling a PlayerEnterPlotEvent
  @Subscribe
  public void onPlayerEnterPlot(PlayerEnterPlotEvent e) {
    //do stuff
  }
}
```

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們力求準確，但請注意，自動翻譯可能包含錯誤或不精確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤釋負責。
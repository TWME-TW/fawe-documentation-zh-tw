<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "b7493cdea743931a3aa8213aec544ea9",
  "translation_date": "2025-05-13T03:56:51+00:00",
  "source_file": "plotsquared/api/api-documentation.md",
  "language_code": "tw"
}
-->
# API 文件說明

## Maven 與 Gradle 範例

* Javadocs: [intellectualsites.github.io/plotsquared-javadocs](https://intellectualsites.github.io/plotsquared-javadocs)
* 主要升級差異: [intellectualsites.github.io/plotsquared-api-diff](https://intellectualsites.github.io/plotsquared-diff/)

{% hint style="tip" %}
使用 PlotSquared API 時推薦使用 Gradle。請確保 [toolchain](https://docs.gradle.org/current/userguide/toolchains.html) 指向 Java 17 或更高版本。
{% endhint %}

{% hint style="info" %}
如果你想使用快照版本，請在 repositories 區塊中加入 S01 OSS Sonatype (`https://s01.oss.sonatype.org/`) 的倉庫。
{% endhint %}

### Gradle - PlotSquared Core

如果你需要存取 PlotSquared 的 Bukkit 模組，請複製以下範例。

```kotlin
repositories {
    mavenCentral()
    maven("https://repo.papermc.io/repository/maven-public/")
}

dependencies {
    implementation(platform("com.intellectualsites.bom:bom-newest:1.52"))
    compileOnly("com.intellectualsites.plotsquared:plotsquared-core")
}
```

### Gradle - PlotSquared Core 和 Bukkit

```kotlin
repositories {
    mavenCentral()
    maven("https://repo.papermc.io/repository/maven-public/")
}

dependencies {
    implementation(platform("com.intellectualsites.bom:bom-newest:1.52"))
    compileOnly("com.intellectualsites.plotsquared:plotsquared-core")
    compileOnly("com.intellectualsites.plotsquared:plotsquared-bukkit") { isTransitive = false }
}
```

### Maven - PlotSquared Core

```xml
<repositories>
    <repository>
        <id>papermc</id>
        <url>https://repo.papermc.io/repository/maven-public/</url>
    </repository>
</repositories>
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.intellectualsites.bom</groupId>
            <artifactId>bom-newest</artifactId>
            <version>1.52</version>
            <scope>import</scope>
            <type>pom</type>
        </dependency>
    </dependencies>
</dependencyManagement>
<dependencies>
    <dependency>
        <groupId>com.intellectualsites.plotsquared</groupId>
        <artifactId>plotsquared-core</artifactId>
        <scope>provided</scope>
    </dependency>
</dependencies>
```

### Maven - PlotSquared Core 和 Bukkit

```xml
<repositories>
    <repository>
        <id>papermc</id>
        <url>https://repo.papermc.io/repository/maven-public/</url>
    </repository>
</repositories>
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.intellectualsites.bom</groupId>
            <artifactId>bom-newest</artifactId>
            <version>1.52</version>
            <scope>import</scope>
            <type>pom</type>
        </dependency>
    </dependencies>
</dependencyManagement>
<dependencies>
<dependency>
    <groupId>com.intellectualsites.plotsquared</groupId>
    <artifactId>plotsquared-core</artifactId>
    <scope>provided</scope>
</dependency>

<dependency>
    <groupId>com.intellectualsites.plotsquared</groupId>
    <artifactId>plotsquared-bukkit</artifactId>
    <scope>provided</scope>
    <exclusions>
        <exclusion>
            <artifactId>plotsquared-core</artifactId>
            <groupId>*</groupId>
        </exclusion>
    </exclusions>
</dependency>
</dependencies>
```

### PlotSquared 常用類別

* [PlotAPI](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/PlotAPI.java)
* [PlotPlayer](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/player/PlotPlayer.java)
* [FlagContainer](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/plot/flag/FlagContainer.java)
* [SchematicHandler](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/util/SchematicHandler.java)
* [ChunkManager](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/util/ChunkManager.java)
* [UUIDPipeline](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/uuid/UUIDPipeline.java)

## 教學

* [取得 PlotSquared 實例](event-api.md#getting-an-instance)
* [Flag API](flag-api.md)
* [Event API](event-api.md)

{% hint style="tip" %}
如果你有撰寫教學或是為 PlotSquared 製作外掛，並希望我們把連結放在這裡，請建立一個 issue。我們非常感激！
{% endhint %}

## 專有名詞

### 地塊區域

地塊區域是指 PlotSquared 管理/處理的任何區域。如果這是一個無限的地塊世界，整個世界都會被視為地塊區域。如果你使用地塊群集，則只有世界的一部分會是地塊區域，區域外的範圍則不會被 PlotSquared 管理。

參見: [PlotAreaManager.java](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/plot/world/PlotAreaManager.java)`#getPlotAreaByString(...)`

### Clusters

Clusters can be created within existing plot areas, or they can be created in a previously non-plot world, which will in turn create it's own plot area.

See: [PlotCluster.java](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/plot/PlotCluster.java)
See: [PlotSquared.java](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/PlotSquared.java)

### Road

A road is what separates each plot, and includes the wall around each plot. Attempting to get a plot at this location will return null.

See: [Location.java](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/location/Location.java)`#isPlotRoad(...)`

### Plot

A plot can be claimed or unclaimed. Getting a plot at a location where one isn't claimed will return a new unowned plot object.

See: [PlotArea.java](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/plot/PlotArea.java)`#getPlots(...)`

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於準確性，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤譯負責。
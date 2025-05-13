<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "1a99a7a9ca63098b57dc6b59b9a394c4",
  "translation_date": "2025-05-13T03:50:36+00:00",
  "source_file": "fastasyncworldedit/API/api-usage.md",
  "language_code": "tw"
}
-->
# API 使用說明

## Maven 與 Gradle 範例

JavaDocs: [https://intellectualsites.github.io/fastasyncworldedit-javadocs/](https://intellectualsites.github.io/fastasyncworldedit-javadocs/)

WorldEdit 的文件大部分也適用於 FAWE，你可以在這裡找到：[https://worldedit.enginehub.org/en/latest/api/index.html](https://worldedit.enginehub.org/en/latest/api/index.html)

我們建議 FAWE 的操作盡量非同步完成。從主執行緒使用 FAWE API 很可能會阻塞主執行緒，只要正確使用 FAWE。`Operations#complete`（以及其他 `Operations` 方法）是阻塞式的，`EditSession#close` 也是，所以任何你想在編輯後執行的操作，都應該放在關閉 EditSession（使用 close()、try-with-resources 等）之後。務必確保 EditSessions 在進行其他操作前已經關閉，且不要重複使用 EditSessions，否則變更可能不會即時寫入世界。

{% hint style="info" %}
此 API 需要在開發時使用 Java 21，請確保你的工具鏈指向 Java 21。
{% endhint %}

如果你在找快照版本，請將 S01 OSS Sonatype 的倉庫加入 repositories 區塊。

### Gradle - FAWE Core

```kt
repositories {
    mavenCentral()
    maven("https://repo.papermc.io/repository/maven-public/")
    maven("https://maven.enginehub.org/repo/")
}

dependencies {
    implementation(platform("com.intellectualsites.bom:bom-newest:1.52")) // Ref: https://github.com/IntellectualSites/bom 
    compileOnly("com.fastasyncworldedit:FastAsyncWorldEdit-Core")
}
```

### Gradle - FAWE Bukkit 與 Core

```kt
repositories {
    mavenCentral()
    maven("https://repo.papermc.io/repository/maven-public/")
    maven("https://maven.enginehub.org/repo/")
}

dependencies {
    implementation(platform("com.intellectualsites.bom:bom-newest:1.52")) // Ref: https://github.com/IntellectualSites/bom 
    compileOnly("com.fastasyncworldedit:FastAsyncWorldEdit-Core")
    compileOnly("com.fastasyncworldedit:FastAsyncWorldEdit-Bukkit") { isTransitive = false }
}
```

### Maven - Fawe Core

```xml
<repositories>
    <repository>
        <id>papermc</id>
        <url>https://repo.papermc.io/repository/maven-public/</url>
    </repository>
    <repository>
        <id>enginehub</id>
        <url>https://maven.enginehub.org/repo/</url>
    </repository>
</repositories>
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.intellectualsites.bom</groupId>
            <artifactId>bom-newest</artifactId> <!--  Ref: https://github.com/IntellectualSites/bom -->
            <version>1.52</version>
            <scope>import</scope>
            <type>pom</type>
        </dependency>
    </dependencies>
</dependencyManagement>
<dependency>
  <groupId>com.fastasyncworldedit</groupId>
  <artifactId>FastAsyncWorldEdit-Core</artifactId>
  <scope>provided</scope>
</dependency>
```

### Maven - FAWE Bukkit 與 Core

```xml
<repositories>
    <repository>
        <id>papermc</id>
        <url>https://repo.papermc.io/repository/maven-public/</url>
    </repository>
    <repository>
        <id>enginehub</id>
        <url>https://maven.enginehub.org/repo/</url>
    </repository>
</repositories>
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.intellectualsites.bom</groupId>
            <artifactId>bom-newest</artifactId> <!--  Ref: https://github.com/IntellectualSites/bom -->
            <version>1.52</version>
            <scope>import</scope>
            <type>pom</type>
        </dependency>
    </dependencies>
</dependencyManagement>
<dependencies>
    <dependency>
      <groupId>com.fastasyncworldedit</groupId>
      <artifactId>FastAsyncWorldEdit-Core</artifactId>
      <scope>provided</scope>
    </dependency>

    <dependency>
        <groupId>com.fastasyncworldedit</groupId>
        <artifactId>FastAsyncWorldEdit-Bukkit</artifactId>
        <scope>provided</scope>
        <exclusions>
            <exclusion>
                <artifactId>FastAsyncWorldEdit-Core</artifactId>
                <groupId>*</groupId>
            </exclusion>
        </exclusions>
    </dependency>
</dependencies>
```

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們力求準確，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤譯負責。
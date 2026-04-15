<p align="center">
  <img src="../assets/fabrikt-horizontal-final.png" alt="fabrikt" height="80">
</p>

<p align="center"><b>OpenAPI 3 → idiomatic Kotlin. Not a scaffold — a permanent build step.</b></p>

<p align="center">
  <a href="https://central.sonatype.com/artifact/io.fabrikt/fabrikt"><img src="https://img.shields.io/maven-central/v/io.fabrikt/fabrikt?style=flat-square&color=7c3aed" alt="Maven Central"></a>
  <a href="https://github.com/fabrikt-io/fabrikt/stargazers"><img src="https://img.shields.io/github/stars/fabrikt-io/fabrikt?style=flat-square&color=7c3aed" alt="GitHub Stars"></a>
  <a href="https://github.com/fabrikt-io/fabrikt/graphs/contributors"><img src="https://img.shields.io/github/contributors/fabrikt-io/fabrikt?style=flat-square&color=7c3aed" alt="Contributors"></a>
  <a href="https://github.com/fabrikt-io/fabrikt/blob/master/LICENSE"><img src="https://img.shields.io/github/license/fabrikt-io/fabrikt?style=flat-square&color=7c3aed" alt="License"></a>
</p>

---

fabrikt generates null-safe Kotlin models, HTTP clients, and server controllers directly from your OpenAPI 3 spec. Wire it into your build once and your code and contract stay in sync as your API evolves — no manual updates, no drift.

### **[→ Try it in the Playground](https://try.fabrikt.io)**
*Paste your OpenAPI spec and see what gets generated. No installation required.*

---

### What gets generated

| | Output | Frameworks / Libraries |
|---|---|---|
| **Models** | Jackson or Kotlinx.serialization data classes | Null safety · Sealed classes · Polymorphism · JSON Merge Patch |
| **Clients** | Type-safe HTTP clients | OkHttp · OpenFeign · Spring HTTP Interface · Ktor |
| **Controllers** | Annotated server interfaces | Spring MVC · Micronaut · Ktor |

---

### Quick start

The easiest integration is the [Gradle plugin](https://github.com/acanda/fabrikt-gradle-plugin):

```kotlin
// build.gradle.kts
plugins {
    id("ch.acanda.gradle.fabrikt") version "1.31.2"
}

fabrikt {
    generate("api") {
        apiFile = file("src/main/openapi/api.yaml")
        basePackage = "com.example"
    }
}
```

Also available as a custom Gradle task, Maven exec plugin, CLI jar, or Docker image.
[→ Full usage guide & configuration options](https://github.com/fabrikt-io/fabrikt#usage-instructions)

---

**[fabrikt-io/fabrikt](https://github.com/fabrikt-io/fabrikt)** &nbsp;·&nbsp; **[Maven Central](https://central.sonatype.com/artifact/io.fabrikt/fabrikt)** &nbsp;·&nbsp; **[Issues](https://github.com/fabrikt-io/fabrikt/issues)** &nbsp;·&nbsp; **[Discussions](https://github.com/fabrikt-io/fabrikt/discussions)**

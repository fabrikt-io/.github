# fabrikt

**OpenAPI 3 → production-ready Kotlin. Permanently wired into your build.**

[![Maven Central](https://img.shields.io/maven-central/v/io.fabrikt/fabrikt?style=flat-square&color=7c3aed)](https://central.sonatype.com/artifact/io.fabrikt/fabrikt)
[![GitHub Stars](https://img.shields.io/github/stars/fabrikt-io/fabrikt?style=flat-square&color=7c3aed)](https://github.com/fabrikt-io/fabrikt/stargazers)
[![Contributors](https://img.shields.io/github/contributors/fabrikt-io/fabrikt?style=flat-square&color=7c3aed)](https://github.com/fabrikt-io/fabrikt/graphs/contributors)
[![License](https://img.shields.io/github/license/fabrikt-io/fabrikt?style=flat-square&color=7c3aed)](https://github.com/fabrikt-io/fabrikt/blob/master/LICENSE)

---

fabrikt takes an OpenAPI 3 spec and generates idiomatic, null-safe Kotlin — models, HTTP clients, and server controllers — for the frameworks you already use. More than a bootstrapping tool, it stays wired into your build and keeps code and contract in sync as your API evolves.

### What gets generated

| | Output | Frameworks / Libraries |
|---|---|---|
| **Models** | Jackson or Kotlinx.serialization data classes | Null safety · Sealed classes · Polymorphism · JSON Merge Patch |
| **Clients** | Type-safe HTTP clients | OkHttp · OpenFeign · Spring HTTP Interface · Ktor |
| **Controllers** | Annotated server interfaces | Spring MVC · Micronaut · Ktor |

### Quick start

```kotlin
// build.gradle.kts
val fabrikt: Configuration by configurations.creating

tasks.register<JavaExec>("generateCode") {
    inputs.files("src/main/openapi/api.yaml")
    outputs.dir("build/generated")
    classpath(fabrikt)
    mainClass.set("com.cjbooms.fabrikt.cli.CodeGen")
    args = listOf(
        "--output-directory", "build/generated",
        "--base-package",     "com.example",
        "--api-file",         "src/main/openapi/api.yaml",
        "--targets",          "http_models",
        "--targets",          "client",
        "--targets",          "controllers"
    )
}

dependencies {
    fabrikt("io.fabrikt:fabrikt:+") // pin this in production
}
```

Or use the [Gradle plugin](https://github.com/acanda/fabrikt-gradle-plugin), Maven exec plugin, CLI jar, or Docker image — see the [full usage guide](https://github.com/fabrikt-io/fabrikt#usage-instructions).

---

**[→ fabrikt-io/fabrikt](https://github.com/fabrikt-io/fabrikt)** &nbsp;·&nbsp; **[Try it in the Playground](https://try.fabrikt.io)** &nbsp;·&nbsp; **[Maven Central](https://central.sonatype.com/artifact/io.fabrikt/fabrikt)** &nbsp;·&nbsp; **[Report an issue](https://github.com/fabrikt-io/fabrikt/issues)**

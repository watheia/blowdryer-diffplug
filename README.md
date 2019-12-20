
# DiffPlug [Blowdryer](https://github.com/diffplug/blowdryer) scripts

[![License Apache 2.0](https://img.shields.io/badge/license-apache--2.0-brightgreen.svg)](https://tldrlegal.com/license/apache-license-2.0-(apache-2.0))
[![Changelog](https://img.shields.io/badge/keepachangelog-yes-brightgreen.svg)](#changelog)
[![](https://jitci.com/gh/diffplug/blowdryer-diffplug/svg)](https://jitci.com/gh/diffplug/blowdryer-diffplug)

## Available scripts (without `.gradle` extension)

- **spotless/freshmark** - applies to `*.gradle` and `*.md`
- **spotless/java** - applies to `*.gradle` and java sourcesets
  - `干.proj('license', 'supported: apache')`
- **base/java8** - sets up java 8 with UTF-8, clean eclipse projects, and mavenCentral
- **base/changelog** - pulls version information from a changelog in either the same project or the parent project
- **base/gradle-plugin** - sets up gradle plugin metadata and plugin portal publishing, fixes eclipse to hook gradle
  - requires `id 'com.gradle.plugin-publish' version '0.10.1'`
  - `干.proj('git_url', 'the git url with no protocol, e.g.: github.com/diffplug/blowdryer')`
  - `干.proj('plugin_list', 'space-delimited list of plugin names')`
    - `干.proj("plugin_${plugin}_id", "for ${plugin}: apply plugin: 'id'")`
    - `干.proj("plugin_${plugin}_impl", "for ${plugin}: implementationClass")`
    - `干.proj("plugin_${plugin}_name", "for ${plugin}: name for the plugin portal")`
    - `干.proj("plugin_${plugin}_desc", "for ${plugin}: description for the plugin portal")`
- **base/maven** - sets up maven-publish and javadoc
  - `干.proj('git_url', 'the git url with no protocol, e.g.: github.com/diffplug/blowdryer')`
  - `干.proj('maven_group', 'the maven group, recommend com.diffplug')`
  - `干.proj('maven_artifact', 'the maven artifactId')`
  - `干.proj('maven_name', 'human-friendly name')`
  - `干.proj('maven_desc', 'human-friendly description')`
  - `干.proj('javadoc_links', "space-delimited links, if you add '/package-list' to the urls you should get a package list")`
  - `干.proj('license', 'supported: apache')`
- **base/javadoc-agg** - aggregates javadoc from subprojects
  - `干.proj('javadoc_agg', 'space-delimited list of projects containing javadoc to be aggregated')`
  - (also a subset of **base/maven**)
- **base/bintray** - publishes to bintray and mavenCentral
  - requires `id 'com.jfrog.bintray' version '1.8.4'`
  - unless `enable_publishing` is set in `gradle.properties`, this will be skipped
  - `干.proj('bintray_user', 'username for bintray')`
  - `干.proj('bintray_pass', 'password for bintray')`
  - `干.proj('nexus_user', 'username for nexus/mavencentral')`
  - `干.proj('nexus_pass', 'password for nexus/mavencentral')`
  - (also a subset of **base/maven**)
- **base/osgi** - adds OSGi metadata to the jar
  - requires `id 'com.diffplug.gradle.osgi.bndmanifest' version '3.18.1'`
  - `干.proj('osgi_export', '-exportcontents bnd directive')`
  - `干.proj('osgi_symbolic_name', 'Bundle-SymbolicName')`
  - (also a subset of **base/maven**)

## Users

| user                                                                  | updated on  | to version                                                    |
| :-------------------------------------------------------------------- | :---------- | :------------------------------------------------------------ |
| [blowdryer](https://github.com/diffplug/blowdryer)                    | 2019-12-10  | [1.0.0](https://github.com/diffplug/blowdryer-diffplug#100---2019-12-10) |
| [spotless-changelog](https://github.com/diffplug/spotless-changelog)  | 2019-12-10  | [1.0.0](https://github.com/diffplug/blowdryer-diffplug#100---2019-12-10) |
| [durian-globals](https://github.com/diffplug/durian-globals)          | 2019-12-17  | [1.1.0](https://github.com/diffplug/blowdryer-diffplug#100---2019-12-10) |

# Changelog

## [Unreleased]
### Added
- `base/changelog`, which pulls version information from a changelog in either the same project or the parent project
- `base/bintray`, for pushing to bintray and mavenCentral
- `base/osgi`, for OSGi metadata
- `base/javadoc-agg`, for aggregating javadoc from subprojects into one central artifact

### Fixed
- Set javadoc to use `UTF-8` encoding.

## [1.0.0] - 2019-12-10
First release.

<!-- END CHANGELOG -->

# Acknowledgements

- Thanks to [Lars Grefer](https://github.com/larsgrefer) and [Dennis Fricke](https://github.com/Frisch12) for
  - [`JavadocUtf8Plugin`](https://github.com/freefair/gradle-plugins/blob/6d6f5ff6036e7da1c329075a02c6452c0bb669be/maven-plugin/src/main/java/io/freefair/gradle/plugins/maven/javadoc/JavadocUtf8Plugin.java), licensed under the [MIT License](https://github.com/freefair/gradle-plugins/blob/6d6f5ff6036e7da1c329075a02c6452c0bb669be/LICENSE), used [here](https://github.com/diffplug/blowdryer-diffplug/blob/9fcb5e22b9ba2cc1c0884c4fb60b4080687b2435/src/main/resources/base/javadoc-agg.gradle#L38-L41).
  - [`JavadocJarPlugin`](https://github.com/freefair/gradle-plugins/blob/6d6f5ff6036e7da1c329075a02c6452c0bb669be/maven-plugin/src/main/java/io/freefair/gradle/plugins/maven/javadoc/JavadocJarPlugin.java), licensed under the [MIT License](https://github.com/freefair/gradle-plugins/blob/6d6f5ff6036e7da1c329075a02c6452c0bb669be/LICENSE), used [here](https://github.com/diffplug/blowdryer-diffplug/blob/9fcb5e22b9ba2cc1c0884c4fb60b4080687b2435/src/main/resources/base/javadoc-agg.gradle#L52-L60).
- Thanks [Netflix Build Language Plugins (nebula)](https://github.com/nebula-plugins) for [`NebulaAggregateJavadocPlugin`](https://github.com/nebula-plugins/gradle-aggregate-javadocs-plugin/blob/8deca214e2ec2463b7d23c46d17b33edf60a2360/src/main/groovy/nebula/plugin/javadoc/NebulaAggregateJavadocPlugin.groovy), licensed under the [`Apache 2.0 license`](https://github.com/nebula-plugins/gradle-aggregate-javadocs-plugin/blob/8deca214e2ec2463b7d23c46d17b33edf60a2360/LICENSE), used [here](https://github.com/diffplug/blowdryer-diffplug/blob/9fcb5e22b9ba2cc1c0884c4fb60b4080687b2435/src/main/resources/base/javadoc-agg.gradle#L22-L28).

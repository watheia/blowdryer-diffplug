
# DiffPlug [Blowdryer](https://github.com/diffplug/blowdryer) scripts

[![License Apache 2.0](https://img.shields.io/badge/license-apache--2.0-brightgreen.svg)](https://tldrlegal.com/license/apache-license-2.0-(apache-2.0))
[![Changelog](https://img.shields.io/badge/keepachangelog-yes-brightgreen.svg)](#changelog)
[![](https://jitci.com/gh/diffplug/blowdryer-diffplug/svg)](https://jitci.com/gh/diffplug/blowdryer-diffplug)

## Available scripts (without `.gradle` extension)

- **spotless/freshmark** - applies to `*.gradle` and `*.md`
- **spotless/java** - applies to `*.gradle` and java sourcesets
  - `干.proj('license', 'supported: apache')`
- **base/java8** - sets up java 8 with UTF-8, clean eclipse projects, and mavenCentral
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

## Users

| user                                                                  | updated on  | to version                                                    |
| :-------------------------------------------------------------------- | :---------- | :------------------------------------------------------------ |
| [blowdryer](https://github.com/diffplug/blowdryer)                    | 2019-12-10  | [1.0.0](https://github.com/diffplug/blowdryer-diffplug#1.0.0) |
| [spotless-changelog](https://github.com/diffplug/spotless-changelog)  | 2019-12-10  | [1.0.0](https://github.com/diffplug/blowdryer-diffplug#1.0.0) |

# Changelog

## [Unreleased]
### Fixed
- Set javadoc to use `UTF-8` encoding.

## [1.0.0] - 2019-12-10
First release.

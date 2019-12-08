
# DiffPlug [Blowdryer](https://github.com/diffplug/blowdryer) scripts

## Available scripts

| path (without .gradle) | notes                                            |
| :--------------------- | :----------------------------------------------- |
| spotless/freshmark     | applies to `*.gradle` and `*.md` |
| spotless/java          | applies to `*.gradle` and java sourcesets, needs param `license` |
| base/java8             | sets up java 8 with UTF-8, clean eclipse projects, and mavenCentral |
| base/gradle-plugin     | **requires `id 'com.gradle.plugin-publish' version '0.10.1'`**, fixes eclipse to hook gradle integration tests, uses param `git_url` |


## Users

| user                                                                  | updated on  | to version                                                    |
| :-------------------------------------------------------------------- | :---------- | :------------------------------------------------------------ |
| [spotless-changelog](https://github.com/diffplug/spotless-changelog)  | 2019-12-07  | [1.0.0](https://github.com/diffplug/blowdryer-diffplug#1.0.0) |

# Changelog

## [Unreleased]

### Added
- the first feature

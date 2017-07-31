<img src="https://unascribed.com/f/a231ace4_trumpet.png" align="right" width="180px"/>

# Elytra Project Skeleton

[>> Downloads <<](https://github.com/elytra/Skeleton/releases)

*Spooky scary skeletons*

**This mod is open source and under a permissive license.** All Elytra mods are,
and as such, can be included in any modpack on any platform without prior
permission. We appreciate hearing about people using our mods, but you do not
need to ask to use them. See the [LICENSE file](LICENSE) for more details.

**Notice**: The issue template and downloads link on this project, as
well as the open source modpack notice, are here for ease of inclusion
in Skeleton-derived mods, and do not neccessarily apply to Skeleton itself.

A generic Gradle buildfile and a fairly sane project structure to make
getting started easier. Rather than making a new empty directory and
copying your Forge dev files over, just download a copy of this repository.

**Note**: Previous versions of this readme recommended cloning the repo and
keeping the history; this is likely to cause issues and probably shouldn't
be attempted.

Make sure to replace the README.md and decide if the MIT License is what
you want to use. If it is, replace the copyright declaration to have your
name instead of unascribed's.

Don't edit build.gradle, just edit project.gradle.

## Experimental Alternate Setup

Copy Skeleton into your project directory as usual, but replace build.gradle
with the following:

```gradle
buildscript {
	repositories {
		mavenCentral()
		jcenter()
		maven {
			url = "http://files.minecraftforge.net/maven"
		}
		maven {
			url = "https://oss.sonatype.org/content/repositories/snapshots/"
		}
		maven {
			url "https://plugins.gradle.org/m2/"
		}
	}
	dependencies {
		classpath 'net.minecraftforge.gradle:ForgeGradle:2.3-SNAPSHOT'
		classpath 'com.github.jengelman.gradle.plugins:shadow:2.0.0'
		classpath 'gradle.plugin.net.minecrell:licenser:0.3'
		classpath 'org.jetbrains.kotlin:kotlin-gradle-plugin:1.1.3'
	}
}

apply from: 'https://raw.githubusercontent.com/elytra/Skeleton/1.12/build.gradle'
```

This will make the skeleton auto-update, but is possibly a security risk and
requires a download of the build file every single time you run Gradle.

# URL/API Source - OBS Plugin

<div align="center">

[![GitHub](https://img.shields.io/github/license/royshil/obs-urlsource)](https://github.com/royshil/obs-urlsource/blob/main/LICENSE)
[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/royshil/obs-urlsource/push.yaml)](https://github.com/royshil/obs-urlsource/actions/workflows/push.yaml)
[![Total downloads](https://img.shields.io/github/downloads/royshil/obs-urlsource/total)](https://github.com/royshil/obs-urlsource/releases)
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/royshil/obs-urlsource)](https://github.com/royshil/obs-urlsource/releases)

</div>

## Introduction

The URL/API Source plugin is a plugin for [OBS Studio](https://obsproject.com) that allows users to add a media source that fetches data from a URL or API endpoint and displays it as text.

Check out our other plugin [Background Removal](https://github.com/royshil/obs-backgroundremoval) for OBS Studio that removes background from webcam without a green screen.

🚧 Check out our experimental [CleanStream](https://github.com/royshil/obs-cleanstream) OBS plugin for real-time filler word (uh,um) and profanity removal from live audio stream 🚧

If you like this work, which is given to you completely free of charge, please consider supporting it on GitHub: https://github.com/sponsors/royshil

## Download
Check out the [latest releases](https://github.com/royshil/obs-urlsource/releases) for downloads and install instructions.


## Building

The plugin was built and tested on Mac OSX  (Intel & Apple silicon), Windows and Linux.

Start by cloning this repo to a directory of your choice.

### Mac OSX

Using the CI pipeline scripts, locally you would just call the zsh script. By default this builds a universal binary for both Intel and Apple Silicon. To build for a specific architecture please see `.github/scripts/.build.zsh` for the `-arch` options.

```sh
$ ./.github/scripts/build-macos -c Release
```

#### Install
The above script should succeed and the plugin files (e.g. `obs-urlsource.plugin`) will reside in the `./release/Release` folder off of the root. Copy the `.plugin` file to the OBS directory e.g. `~/Library/Application Support/obs-studio/plugins`.

To get `.pkg` installer file, run for example
```sh
$ ./.github/scripts/package-macos -c Release
```
(Note that maybe the outputs will be in the `Release` folder and not the `install` folder like `pakage-macos` expects, so you will need to rename the folder from `build_x86_64/Release` to `build_x86_64/install`)

### Linux (Ubuntu)

Use the CI scripts again
```sh
$ ./.github/scripts/build-linux.sh
```

### Windows

Use the CI scripts again, for example:

```powershell
> .github/scripts/Build-Windows.ps1 -Target x64 -CMakeGenerator "Visual Studio 17 2022"
```

The build should exist in the `./release` folder off the root. You can manually install the files in the OBS directory.

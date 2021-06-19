[![Build Status](https://github.com/malliina/live-reload/workflows/Test/badge.svg)](https://github.com/malliina/live-reload/actions)

# live-reload

Reloads the browser after a code change in your web app.

## Usage

1. Add to `project/plugins.sbt`:

        addSbtPlugin("com.malliina" % "live-reload" % "0.1.0")

1. Enable `LiveReloadPlugin` instead in build.sbt:

        val app = project
          .in(file("."))
          .enablePlugins(LiveReloadPlugin)

1. Inject the JavaScript URL found in value `com.malliina.live.LiveReload.script` to the HTML of your web page.

1. When developing for example http4s apps with `sbt ~reStart`, changes to source code will reload the web page after recompilation.

## Example app

Folder [http4s-app](http4s-app) contains an example http4s app with live reloading enabled.

## Releasing a new version

To release a new version to Maven Central, run:

    sbt release
    
This will push a new tag to version control, which triggers this [GitHub Action](.github/workflows/release.yml) that 
pushes artifacts to Maven Central.

## Prior art

Li Haoyi's [workbench](https://github.com/lihaoyi/workbench):

- Is specific to Scala.js
- Uses libraries I'm not interested in at this time

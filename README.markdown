[![Template ci](https://github.com/alessandrocandolini/android-app.g8/actions/workflows/ci.yml/badge.svg)](https://github.com/alessandrocandolini/android-app.g8/actions/workflows/ci.yml)

# android-app.g8

Opinionated [Giter8](https://www.foundweekends.org/giter8/) template for personal projects involving native Android development in Kotlin. There no attempt at making this close to mainstream industry standards (quite the opposite!) 

[Giter8](https://www.foundweekends.org/giter8/) is a template engine written in the [Scala programming language](https://www.scala-lang.org/), integrated in the Scala build tool ([sbt](https://www.scala-sbt.org/)) and powered by [StringTemplate](https://www.stringtemplate.org/). 
There are plenty of templating tools available (eg, [cookiecutter](https://cookiecutter.readthedocs.io/en/stable/) or [jinjia](https://jinja.palletsprojects.com/) in python, etc) but I've found g8 particularly handy: it has limitations but it tries to encourage a declarative approach to templates. No familiarity with Scala is needed to use or even contribute to the template. 

## How to run it 

Requirements: either [sbt](https://www.scala-sbt.org/) or [g8](https://www.foundweekends.org/giter8/) must be installed in the system. One option to install `sbt` is not use an ephemeral `nix` shell: 
```bash
nix-shell -p sbt 
```
Alternatively, on MACOS it's possible to use `homebrew`
```bash
brew install sbt
```

Once sbt is installed, to generate a new project use
```
sbt new git@github.com:alessandrocandolini/android-app.g8.git --name=<name> --force
```
This will generate a folder `name` (if not already present) and create a new project in it. 

`name` is the only mandatory option here. Unless independently specified, default values for the repo name (`repo_name`) and package (`packaged`) will be provided.  

See http://www.foundweekends.org/giter8/usage.html#Usage for more details on how to use g8

## Contribute to the template

Giter8 crash course: 

* Giter8 generates a project that has exactly the same structure of the [src/main/g8](src/main/g8) folder
* template variables are defined in the [default.properties](src/main/g8/default.properties) file
* template variables can be accessed as `$name of the variable$` (ie, between `$`) from everywhere
* `$` is the reserved symbol, whenever you need to use a `$` for purposes other than referring to a template variable be sure to escape it as `\$`; this is a typical source of errors

A more comprehensive guide here: http://www.foundweekends.org/giter8/Contents+in+Depth.html

Template license
----------------
Written in 2022-2023 by Alessandro Candolini alessandro.candolini@gmail.com

To the extent possible under law, the author(s) have dedicated all copyright and related
and neighboring rights to this template to the public domain worldwide.
This template is distributed without any warranty. See <http://creativecommons.org/publicdomain/zero/1.0/>.

[g8]: http://www.foundweekends.org/giter8/

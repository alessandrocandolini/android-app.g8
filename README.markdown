

# android-app.g8

Opinionated giter8 template for personal short native Android apps in kotlin. No attempt at making this compatible with industry standards (quite the opposite) 

[Giter8](https://www.foundweekends.org/giter8/) is a template engine written in the [Scala programming language](https://www.scala-lang.org/), integrated in the Scala build tool ([sbt](https://www.scala-sbt.org/)) and powered by [StringTemplate](https://www.stringtemplate.org/). 
There are plenty of templating tools available (eg, cookiecutter or jinjia in python, etc) but I find g8 particularly handy: it has limitations but it tries to encourage a declarative approach to templates. You don't need familiarity with Scala to use or even contribute to the template. 

## How to use it 

You need either [sbt](https://www.scala-sbt.org/) or [g8](https://www.foundweekends.org/giter8/) installed in your system to run the template. To install it, you can use for example `nix`: 
```bash
nix-shell -p sbt 
```
Alternatively, on MACOS another option can be to install it via `homebrew`
```
brew install sbt
```

Once sbt is installed, it is possible to generate a new project using 
```
sbt new git@github.com:alessandrocandolini/android-app.g8.git --name=<name> --force
```
This will generate a folder `name` (if not already present) and create a new project in it. 

`name` is the only mandatory option here. If you don't specify the other options, default values for the repo name (`repo_name`) and package (`packaged`) will be assigned.  

See http://www.foundweekends.org/giter8/usage.html#Usage for more details on how to use g8

## Contribute to the template

Giter8 crash course: 

* Giter8 generates a project that has exactly the same structure of the [src/main/g8](src/main/g8) folder
* template variables are defined in the [default.properties](src/main/g8/default.properties) file
* template variables can be accessed as `$name of the variable$` (ie, between `$`) from everywhere
* `$` is the reserved symbol, whenever you need to use a `$` for purposes other than referring to a template variable be sure to escape it as `\$`; this is a typical source of errors

A more comprehensive guide here: http://www.foundweekends.org/giter8/Contents+in+Depth.html

To test the template, giter8 provides a sbt command `g8Test`, which unfortunately has some drawbacks. For this reason, the recommended approach is to test the template by generating a fake project and try to compile with LaTeX the generated code. That's exactly what the github action CI is doing. 

Template license
----------------
Written in 2022-2023 by Alessandro Candolini alessandro.candolini@gmail.com

To the extent possible under law, the author(s) have dedicated all copyright and related
and neighboring rights to this template to the public domain worldwide.
This template is distributed without any warranty. See <http://creativecommons.org/publicdomain/zero/1.0/>.

[g8]: http://www.foundweekends.org/giter8/

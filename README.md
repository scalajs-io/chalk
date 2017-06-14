Chalk API for Scala.js
================================
[chalk](https://www.npmjs.com/package/chalk) - Terminal string styling done right. Much color.

### Description

[colors.js](https://github.com/scalajs-io/colors) used to be the most popular string styling module, but it has serious deficiencies 
like extending String.prototype which causes all kinds of problems. Although there are other ones, 
they either do too much or not enough.

**Chalk is a clean and focused alternative.**

### Build Dependencies

* [SBT v0.13.13](http://www.scala-sbt.org/download.html)

### Build/publish the SDK locally

```bash
 $ sbt clean publish-local
```

### Running the tests

Before running the tests the first time, you must ensure the npm packages are installed:

```bash
$ npm install
```

Then you can run the tests:

```bash
$ sbt test
```

### Examples

```scala
import io.scalajs.npm.chalk._

// style a string") 
println(Chalk.blue("Hello world!")) 
```
<span style="color: blue">Hello World!</span>

```scala
import io.scalajs.npm.chalk._

// compose multiple styles using the chainable API
println(Chalk.blue.bgRed.bold("Hello world!"))
```
<span style="color: blue; background: red; font-weight: bold">Hello World!</span>

```scala
import io.scalajs.npm.chalk._

// pass in multiple arguments
println(Chalk.blue("Hello", "World!", "Foo", "bar", "biz", "baz"))
```
<span style="color: blue">Hello World! Foo bar biz baz</span>

```scala
import io.scalajs.npm.chalk._

// nested styles
println(Chalk.red("Hello", Chalk.underline.bgBlue("World") + "!"))
```
<span style="color: red">Hello <span style="color: blue; text-decoration: underline">World!</span></span>

```scala
import io.scalajs.nodejs.console
import io.scalajs.npm.chalk._

// use it like a function
val error = Chalk.bold.red
console.log(error("Error!"))
```
<span style="color: red; font-weight: bold">Error!</span>

### Artifacts and Resolvers

To add the `Chalk` binding to your project, add the following to your build.sbt:  

```sbt
libraryDependencies += "io.scalajs.npm" %%% "chalk" % "0.4.0"
```

Optionally, you may add the Sonatype Repository resolver:

```sbt   
resolvers += Resolver.sonatypeRepo("releases") 
```
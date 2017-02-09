Chalk API for Scala.js
================================
This is a Scala.js type-safe binding for [chalk](https://www.npmjs.com/package/chalk)

Terminal string styling done right. Much color.

#### Build Dependencies

* [ScalaJs.io v0.3.x](https://github.com/ldaniels528/scalajs.io)
* [SBT v0.13.13](http://www.scala-sbt.org/download.html)

#### Build/publish the SDK locally

```bash
 $ sbt clean publish-local
```

#### Running the tests

Before running the tests the first time, you must ensure the npm packages are installed:

```bash
$ npm install
```

Then you can run the tests:

```bash
$ sbt test
```

#### Examples

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

#### Artifacts and Resolvers

To add the `Chalk` binding to your project, add the following to your build.sbt:  

```sbt
libraryDependencies += "io.scalajs.npm" %%% "chalk" % "1.1.3"
```

Optionally, you may add the Sonatype Repository resolver:

```sbt   
resolvers += Resolver.sonatypeRepo("releases") 
```
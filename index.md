Our mission is to improve the day-to-day experience of the Scala developers. We achieve this by implementing tools and writing documentation and educational material.

Below is a list of projects that the Scala Center funded or supported. You can learn more about the Scala Center at [scala.epfl.ch](https://scala.epfl.ch).

# IDE

[Metals](https://scalameta.org/metals/) provides IDE features to a large number of code editors (VS Code, Sublime, etc.). It does so by implementing and extending the [Language Server Protocol](https://microsoft.github.io/language-server-protocol/) with endpoints for compiling, running, testing, and debugging Scala programs. The resulting communication protocol is the [Build Server Protocol](https://build-server-protocol.github.io/). This protocol was first implemented in [bloop](https://scalacenter.github.io/bloop/), a Scala compiler daemon that can improve the compilation times of Scala projects.

[Scastie](https://scastie.scala-lang.org/) allows you to start using and discovering Scala in your browser without installing anything locally. You can even experiment with community libraries, or different platforms such as [Scala.js](https://www.scala-js.org/). It can also be used to share or to embed code in your documentation.

# Dependency Management

[Scaladex](https://index.scala-lang.org/) is the website that indexes all the open source Scala libraries. It makes it easy for you to find the right library for your particular need, that is compatible with the Scala version and target (JVM, JS or native) you are working with. Scaladex can also answer questions like “what is the latest version of that library?”, “what are the Maven coordinates of this project?”, “is this version of that library compatible with that other library?”, “does this library support that version of Scala?”.

Build tools such as sbt, Mill, or Pants rely on [Coursier](https://get-coursier.io/) to resolve project dependencies. Coursier can resolve, fetch, and launch Scala artifacts.

When a project depends on two libraries which in turn depend on a third library you need to make sure that the two libraries depend on a compatible version of the third one. Otherwise, you may hit runtime errors such as “NoSuchMethodError”. The sbt plugin [sbt-missinglink](https://github.com/scalacenter/sbt-missinglink) can detect these errors without running your program.

# Documentation and Education

The websites [scala-lang.org](https://www.scala-lang.org/) and [docs.scala-lang.org](https://docs.scala-lang.org/) are the places where newcomers expect to find information and documentation on how to use Scala.

In addition to documentation, we also produce [online courses](https://docs.scala-lang.org/learn.html) containing video lectures and assignments. Online courses are typically 6 weeks long (assuming ~5 hours of study per week) and cover topics like the Scala language, functional programming, parallel programming, big data analysis, and reactive systems.

# Scala.js

[Scala.js](http://www.scala-js.org/) makes it possible to execute Scala programs in a JavaScript environment (web browsers or Node.js). The sbt plugin [sbt-scalajs-bundler](https://scalacenter.github.io/scalajs-bundler/) can resolve and download NPM packages and bundles them with your Scala.js application using Webpack.

# Scala Native

[Scala Native](https://scala-native.readthedocs.io/en/v0.3.9-docs/) is an optimizing ahead-of-time compiler and lightweight, managed runtime designed specifically for Scala. It is the Doctoral work of Denys Shabalin at EPFL. The Scala Centre took over the project in January 2020.

Similar to Scala.js, which compiles Scala to JavaScript, Scala Native compiles Scala to native code. It uses LLVM as the back-end target, which then compiles to machine code.

Compiling to machine code means that the resulting executable requires no JVM runtime, which, in turn, means no JVM startup overhead. On the other hand, all kinds of optimisations need to be done ahead-of-time and this is why Scala Native is a challenging project.

# Scala debugging

The Scala Center has started [efforts to improve the debugging experience](https://github.com/scalacenter/advisoryboard/blob/master/proposals/022-jsr-45.md) for Scala programs. To that end, we are looking into how we can properly embed line and maybe column information into the resulting class files and, more importantly, have them be consistent when optimisations like inlining are applied.
Apart from debugging, the functionality mentioned above is also critical for code coverage tools (like JaCoCo). Having the above information embedded into the class files will allow code coverage tools to correctly deduce coverage information for inline functions.

# Migration to Scala 3

Scala 3 will arrive in late 2020, with many changes to source compatibility with Scala 2.13, and some new APIs added to its standard library. [Our work](https://github.com/scala/scala/pull/8865) will enable users of Scala 2.13 to continue to use libraries that have migrated to Scala 3.0 and use a compatible API, giving a long window for projects to migrate one by one. We do this by supporting the TASTy intermediate format.

When you are ready, the [Scala 3 migration guide](https://github.com/scalacenter/scala-3-migration-guide) gives a clear path for upgrading your code base, and outlines which tools can help automate the work required.


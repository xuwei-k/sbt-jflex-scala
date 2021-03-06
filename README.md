# sbt-jflex-scala

A plugin for sbt 0.13.x, generates code based on a jflex specifiaction.

This is inspired by [sbt-jflex](https://github.com/dlwh/sbt-jflex).

## Usage

In your `project/plugins.sbt`,

```scala
resolvers += "Github Repository" at "https://3tty0n.github.io/sbt-jflex-scala/repo/"

addSbtPlugin("com.micchon" % "sbt-jflex-plugin" % "0.1.0-SNAPSHOT")
```

Put your `*.flex` file in `src/main/flex`.

Next, in your sbt shell, type 

```
> jflexGenerate
```

then `Yylex.scala` is generated in `src/main/scala/flex`.

If you want to generate `Yylex.scala` when you compile, in `build.sbt`,

```scala
compile := ((compile in Compile).dependsOn(jflexGenerate)).value
```

## License

MIT
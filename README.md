# Vassal Module Template

* Put custom module source code in `src/`.

* Put the contents of your module in `dist/`.

* `pom.xml` contains project settings, such as the Vassal version to compile against, the name and version of your module.

* Variables defined in `pom.xml` can be substituted into other files, listed explicitly in the `<resources>` section. E.g., you can substitute the module version number into the `moduledata` file:
```
<version>${project.version}</version>
```
and also into to `buildFile.xml`:
```
<VASSAL.build.GameModule ModuleOther1="" ModuleOther2="" VassalVersion="3.7.4" description="Some Module for Some Game" name="SomeModule" nextPieceSlotId="14332" version="${project.version}">
```
in order to keep them current automatically.

* Run Maven's package target to build the module. (From the command line on Unix: `./mvnw package`; from the command line on Windows: `mvnw.cmd package`; from an IDE, choose the "package" target.) The module will be written to `target/`.
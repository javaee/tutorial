# Java EE Tutorial

This repository contains the source files that are used to build the [_Java Platform, Enterprise Edition (Java EE) 8
Tutorial_](https://javaee.github.io/tutorial/). The source files are authored in [AsciiDoc](http://asciidoc.org/).
AsciiDoc is similar to original markdown but is particularly suited for user documentation. This project also uses
[JBake](http://jbake.org/). JBake is a static site generator that is inspired from Jekyll and written in Java.
JBake uses templates for the structure of the page and the body of the page is generated from AsciiDoc content.

Note that the Java EE Tutorial code examples are located in the
[javaee/tutorial-examples](https://github.com/javaee/tutorial-examples) repository.

## Contributing
The easiest way to contribute is by opening an [issue](https://github.com/javaee/tutorial/issues) that contains
feedback and review comments. All issues will be addressed as soon as possible.

The Java EE Tutorial project is also open for contributions and your help is greatly appreciated. If you have an idea
for the tutorial and want to add a section or update an existing section, then review the following links:

* [Contribute](CONTRIBUTING.md)
* [Pull Request Acceptance Workflow](pr_doc_workflow.md)
* [License](LICENSE.md)

## Building the Java EE Tutorial

The following directions explain how to do local builds of the tutorial. Note that any changes that are pushed to the
master branch automatically trigger a build of the site files and tutorial sources. The results are automatically
pushed to the gh-pages branch. You can view the published site at https://javaee.github.io/tutorial/.

### Pre-Requisites

- Maven
- JDK8+

Note that manually deploying the site requires password-less authentication. This is done by exporting your SSH public
key into your GitHub account.

### Build the Site Locally

The site is generated under `target/staging`. Open `file:///PATH_TO_PROJECT_DIR/target/staging` in a browser to view
the output.

```
mvn generate-resources
```

You can also invoke the JBake plugin directly:

```
mvn jbake:build
```

#### Rebuild the Site on Changes

The following command builds the site and, if kept running, detects changes to the sources and incrementally renders
the site. This is convenient when writing content.

```
mvn jbake:watch
```

#### Serve the Site locally

If a web server is required (for example, absolute paths are used), you can use the following command to start a
Jetty web server at `http://localhost:8820`. The command also watches for changes and rebuilds incrementally.

```
mvn jbake:serve
```


### Deploy the Site to Github Pages

If you want to manually push a build to the gh-pages branch, use:

```
mvn deploy -Ppublish-site
```

### Produce a Zip File for Download

To produce a zip file containing the generated HTML files, use:

```
mvn package
```

When making a release on GitHub, this zip file should be added to the release.

## Links

- [JBake maven plugin documentation](https://github.com/Blazebit/jbake-maven-plugin)
- [JBake documentation](http://jbake.org/docs/2.5.1)
- [Freemarker documentation](http://freemarker.org/docs)
- [AsciiDoc User Guide](http://asciidoc.org/userguide.html)
- [Asciidoctor quick reference](http://asciidoctor.org/docs/asciidoc-syntax-quick-reference)

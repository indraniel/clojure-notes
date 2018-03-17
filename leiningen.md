# Notes on [Leiningen][0]

## Basic Docs

* [Tutorial](https://github.com/technomancy/leiningen/blob/master/doc/TUTORIAL.md)
* [FAQ](https://github.com/technomancy/leiningen/blob/master/doc/FAQ.md)
* [Deploy](https://github.com/technomancy/leiningen/blob/master/doc/DEPLOY.md)

## External Resources

* [Managing Native Dependencies (`.so`, `.dll`, etc.) with Leiningen](https://nakkaya.com/2010/04/05/managing-native-dependencies-with-leiningen/)
    * [Native Dependencies for Sigar](https://github.com/zcaudate-me/sigar-native-deps)
    * [stackoverflow: Howto package my project resource-paths to use as project dependency?](https://stackoverflow.com/questions/23020288/howto-package-my-project-resource-paths-to-use-as-project-dependency)

* [stackoverflow: Resources in Clojure applications](https://stackoverflow.com/questions/8009829/resources-in-clojure-applications?rq=1)

## Unique Development Libraries

* [Loading Clojure Libraries Directly From Github](https://lambdaisland.com/blog/17-05-2017-loading-clojure-libraries-directly-from-github)

## Maven/ `.m2` / local-repo path adjustments

* [clojure lein 2: change local-repo path](https://coderwall.com/p/bvm4ag/clojure-lein-2-change-local-repo-path)
* [stackoverflow: Determining Clojure Jar Path](https://stackoverflow.com/questions/9707413/determining-clojure-jar-path) -- _provides a quick understanding of maven directory structure_
* [Overriding local repository location for an individual project](https://stackoverflow.com/questions/11460283/how-can-i-make-leiningen-2-respect-the-local-repository-path-in-mavens-settings)
* [Maven - alternative `.m2` directory](https://stackoverflow.com/questions/16591080/maven-alternative-m2-directory) -- _provides generic maven adjustments_
* [Leiningen: How to customize the location of the `.m2` folder](https://stackoverflow.com/questions/12579335/leiningen-how-to-customize-the-location-of-the-m2-folder)
* [Leiningen: working with local repository](http://www.spacjer.com/blog/2015/03/23/leiningen-working-with-local-repository/)

## Fundamental Understanding

* [What is Leiningen doing underneath the hood with the JVM calls](https://stackoverflow.com/questions/11973694/how-to-add-directory-to-clojures-classpath)
* [How Clojure Babies Are Made: Understanding `lein run`](http://www.flyingmachinestudios.com/programming/how-clojure-babies-are-made-lein-run/)
* [How Clojure Babies are Made: Leiningen's Trampoline](http://www.flyingmachinestudios.com/programming/lein-trampoline/)

### Appreciating the differences between `lein run`, `lein trampoline`, and `lein uberjar`

* **`lein run`** : executes the `-main` function of the targeted or default namespace. Lein runs through out the full execution of that main methods so if your main function creates a web servers, then the leiningen process also stays up the whole time.
* **`lein trampoline`** : executes the `-main` function as a separate process, so that the main leiningen process can exit and therefore you only have one process running
* **`lein uberjar`** : creates a standalone jar file, so that any other user does not need to have lein installed to run your code. (or any of the source files). To run the jar, you execute `java -jar myjarname.jar` which contains all the source and all the dependencies.


## Project Structure

* [How To Organize A Clojure Project And Its Dependencies](https://cb.codes/organizing-clojure-projects-and-libraries/)

## Customizations

* [Clojure Templates Are Easy With Leiningen](http://jr0cket.co.uk/2015/03/clojure-templates-are-easy-with-leiningen.html)

## Miscellaneous

### Other Tutorials (maybe outdated)

* [Using Leiningen to build Clojure code](http://alexott.net/en/clojure/ClojureLein.html)

### Leiningen Alternatives

* [Deps and CLI Guide](https://clojure.org/guides/deps_and_cli)
* [Clojure Projects From Scratch](https://oli.me.uk/2018-02-26-clojure-projects-from-scratch/) -- _how to structure a project with the new Clojure CLI + [deps.edn](https://clojure.org/guides/deps_and_cli)_

### Other types of projects

* [Introduction to OpenCV Development with Clojure](http://www.swarthmore.edu/NatSci/mzucker1/opencv-2.4.10-docs/doc/tutorials/introduction/clojure_dev_intro/clojure_dev_intro.html) -- _is an interesting guide to using native libraries with leiningen and clojure_



[0]: https://leiningen.org/

# lein-spring-boot-jar

**Experimental**

A Leiningen plugin for building a spring-boot runnable jar similar to
`spring-boot-gradle-plugin` `spring-boot-maven-plugin`


## Install

Clone this project and run `lein install` to install the plugin locally to your `.m2` directory

## Usage

Put `[lein-spring-boot-jar "0.1.0"]` into the `:plugins` property of your project.

```clojure
(defproject myproject "0.1.0-SNAPSHOT"
  :plugins [[lein-spring-boot-jar "0.1.0"]]
  :repositories [["spring-milestone" "https://repo.spring.io/milestone"]]
  :main "my.project.app"
  :jar-name myproject.jar
  :spring-boot-loader-version "2.1.2.RELEASE"
  :aot :all)
```


Build a spring executable jar

    $ lein spring-boot-jar
    $ java -jar target/boot-myproject.jar


Example project https://github.com/scotthaleen/clojure-spring-cloud

## Notes

Project Settings

    :main ;; Required to build the manifest for the jar
    :aot :all ;; required
    ;; you will likely need to add the "spring milestone to :repositories
    :repositories [["spring-milestone" "https://repo.spring.io/milestone"]]
    :jar-name ;; Will prepend "boot-" to project jar-name as the jar file
    :spring-boot-loader-version "2.1.2.RELEASE" ;; Optional, will default to 2.1.2.RELEASE


## License

Copyright © 2019 Scott Haleen

Distributed under the Eclipse Public License, the same as Clojure.

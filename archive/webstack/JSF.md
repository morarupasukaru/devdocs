# JSF

JSF (Jakarta Server Faces or previously JavaServer Faces) is/was the Java EE standard framework to build web application in Java.

* Getting Started: 
  checkout JSF & PrimeFaces tutorials at 
  [codenotfound.com](https://codenotfound.com/jsf-primefaces-tutorials) and [git repo](https://github.com/code-not-found/jsf-primefaces)
  to have quite up-to-date maven builds
* Versions
  * latest version is [JSF is 2.3](https://javaee.github.io/javaserverfaces-spec/) for [JAVA EE 8](https://www.oracle.com/java/technologies/java-ee-8.html)
  * Oracle handed Java EE and JSF to Eclipse foundation around 2017 and Java EE and JavaServer Faces have been renamed to Jakarta EE and Jakarta Server Faces
* JSF Concepts
  * JSF is based on [model-view-controller](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) design pattern
    but other mvc pattern like [model-view-presenter](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93presenter) can be used as well
  * web pages (*.xhtml) are written with [facelets](https://en.wikipedia.org/wiki/Facelets) web template system
    * web pages should habe `.xhtml` extension (default)
    * JSF Web pages are HTML with JSF tag from tag libraries
    * [various tag libraries are supported by Facelets](https://www.javatpoint.com/facelets) 
      like `xmlns:h="http://xmlns.jcp.org/jsf/html"` to integrate UI components; e.g. `<h:inputText>`
    * [JSF expression language](https://eclipse-ee4j.github.io/jakartaee-tutorial/#expression-language) 
      is used to access properties of managed beans (e.g. `#{myBean.property}`) and other functions
  * [managed beans](https://www.javatpoint.com/jsf-managed-beans) are POJO and are registered/managed by JSF 
    * managed beans are normally the model of web page and contains business logic
    * public no-arg constructor is required
    * properties must be available public with getter/setter
    * [@ManagedBean](https://javaee.github.io/javaee-spec/javadocs/javax/faces/bean/ManagedBean.html) 
      annotation register automatically the bean with a given name
    * [managed beans scope](https://eclipse-ee4j.github.io/jakartaee-tutorial/#using-managed-bean-scopes) define the 
      scope within a managed beans is stored: application scope (all user), session scope (session, current user), etc.
      request scope (web request; default scope)
      * scope are define by setting an annotation like @ApplicationScoped on the managed beans
  * web.xml: a web deployment descriptor contains the configuration of servlets required to process JSF requests
  * [faces-config.xml: application configuration files](https://eclipse-ee4j.github.io/jakartaee-tutorial/#application-configuration-resource-file) can configure object that cannot be annotated like i18n bundle
  * [validation](https://www.javatpoint.com/jsf-validation) tags are provided with `xmlns:f="http://xmlns.jcp.org/jsf/core"`
    * custom validation with [method in managed beans](https://eclipse-ee4j.github.io/jakartaee-tutorial/#bean-validation) 
      or with a [custom Validator](https://eclipse-ee4j.github.io/jakartaee-tutorial/#registering-a-custom-validator)
  * navigation by written an [action method on managed beans](https://eclipse-ee4j.github.io/jakartaee-tutorial/#writing-a-method-to-handle-navigation) 
    that returns a String containing of the new page to display
  * [h:outputScript or h:outputStylesheet](https://eclipse-ee4j.github.io/jakartaee-tutorial/#resource-relocation-using-houtputscript-and-houtputstylesheet-tags)
    allow to load external JavaScript or CSS file
  * etc. (current doc is a quick JSF summary)
* Ecosystem 
  * application server: [Tomcat](http://tomcat.apache.org/) 
    (tomcat is not a full Java EE server therefore JSF jars must be provided in WAR)
  * ui components library: [PrimeFaces](https://www.primefaces.org/), [ButterFaces](http://butterfaces.org/)
  * utility library: [OmniFaces](https://showcase.omnifaces.org/)
* Resources
  * disclaimer: *it's quite hard to find complete well-written JSF documentation on internet*
  * tutorials:
    * [petstore JSF demo](https://github.com/xtremebiker/petstore)
    * [JSF & PrimeFaces tutorials](https://codenotfound.com/jsf-primefaces-tutorials) with [git repo](https://github.com/code-not-found/jsf-primefaces)
    * [javatpoint](https://www.javatpoint.com/jsf-tutorial)
    * [java EE 5](https://docs.oracle.com/javaee/5/tutorial/doc/index.html)
    * [jakarta EE 9](https://eclipse-ee4j.github.io/jakartaee-tutorial/)
    * [JSF with Spring](https://www.baeldung.com/spring-jsf)
  * references
    * [summary of Java EE 6 JSF exam (1Z0-896)](https://bitbucket.org/paulstat/oracle-jsf-expert-1z0-896/wiki/Home)
    * [oracle documentation](https://www.oracle.com/java/technologies/javaserverfaces.html)
    * [legacy Java EE archives](https://javaee.github.io/)
      for anyone who wishes to browse the extensive history, prior to contribution to Eclipse
  * course: [JSF 2.2 - Java Server Faces for Beginners - Build a DB App](https://www.udemy.com/course/jsf-tutorial/)

[*Go to parent page*](README.md)

*(Page mainly written in March 2021; links checked on 12.02.2024)*

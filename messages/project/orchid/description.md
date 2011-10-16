The main idea with this project is to create tools for web content management applications. The content are stored in 
regular files (properties, text, html) which is stored in a file system. The main benefit of this is that the content
can be versioned by GIT. The goal is to have multiple publishers and authoring tools developed for multiple languages 
and web frameworks as described in the following picture.

![Orchid Overview]({link:/resources/images/orchid.png})

Currently the following modules are available:

**se.softhouse.garden.orchid.commons**

This module contains a property load which can load messages from a directory structure. It uses the same structure
as used by properties in java except that the key is the path to the file, i.e. the property key a.b.c.d maps
to the file a/b/c/d.txt where the suffix might differ. The filename might also contain the locale name,
e.g. d_en_US.txt. It is also possible to add property files in the structure, they are then interpreted and 
inserted in the hierarchy, e.g. a/b/c.properties. The properties are accessed using the MessageFormat class available
in the JDK. The properties might contain the same syntax as provided by MessageFormat and an extension which makes
it possible to use named arguments instead of numbered arguments.

**se.softhouse.garden.orchid.spring**

This module contains some utilities for Spring MVC:

* Extensions to the MessageSource bean to support the OrchidMessageFormat and OrchidDirectoryLoader provided in the commons module. </li>
* Tags and beans for inserting texts with named arguments.
* Beans which can used to create links.

This site is implemented using the orchid spring module and can be used as an example application.
See project [Garden Web]({link:/project/garden}) for information about how to access the source.

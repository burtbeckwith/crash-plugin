A plugin for grails to include [the Common Reusable SHell (CRaSH)][1]
=====================================================================

# Installation
Just install the plugin with e.g. `grails install-plugin crash` to embed CRaSH into your grails application.
It includes the ssh shell and by default listens on port 2000 with the username/password 'admin'.
So make sure to change that for production!

# Configuration

To start up CRaSH, a spring bean named `crashSpringWebBootstrap` of type `SpringWebBootstrap` is defined.
Its config properties can be set by assigning a map of config properties to `grails.plugin.crash.config`, e.g.:

    grails.plugin.crash.config = [
            'crash.ssh.port': 2001,
            'crash.auth.simple.password': 'secretPassword'
    ]

To include telnet support include the following dependency in your own BuildConfig:

    runtime 'org.crsh:crsh.shell.telnet:1.2.0-cr3'

  [1]: http://www.crashub.org/

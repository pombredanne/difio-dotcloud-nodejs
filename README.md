This is a node.js client side agent for monupco.com that is preconfigured for dotCloud deployments.


Installing on your dotCloud node.js application
----------------------------------------------

- Create an account at http://monupco.com

- Add a dependency in your package.json file

    ...
    "dependencies": {
        ...
        "monupco-dotcloud-nodejs": ""
    },
    ...

- Enable the registration script in your app postinstall hook. From the approot directory:


    [ ! -f postinstall ] && echo '#!/bin/sh' > postinstall && chmod +x postinstall
    echo '`npm bin`/monupco-dotcloud' >> postinstall


- Set your monupco user id ( you can get it from https://monupco-otb.rhcloud.com/profiles/mine/ ).

    dotcloud var set <app name> MONUPCO_USER_ID=<Your monupco user id>


- Push your application

    dotcloud push <app name>

- That's it, you can now checkout your application statistics at http://monupco.com

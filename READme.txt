IMPORTANT: After startup, the webapp automatically opens in your browser (http://localhost:3006). However, you must hard refresh the page before any content is rendered.

.Prerequisites
|===
|Requirement |Version
|NodeJS
|>= 10
|===
TIP: Use https://github.com/creationix/nvm/blob/master/README.md[nvm] to manage NodeJS versions locally.
[source,shell]
----
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
$ . ~/.nvm/nvm.sh
$ nvm install 10
$ nvm use 10
----
== Basic setup
:numbered:
=== Clone the project
First you need to clone the https://github.com/integr8ly/tutorial-web-app-walkthroughs[walkthroughs repository] next to the tutorial web app:
[source,shell]
----
$ git clone https://github.com/integr8ly/tutorial-web-app-walkthroughs.git
$ git clone https://github.com/integr8ly/tutorial-web-app.git
----
=== Install dependencies
Then change to the webapp directory, install its dependencies and run the development server.  
[source,shell]
----
$ cd tutorial-web-app
$ rm -rf node_modules
$ npm install -g yarn
$ yarn install
$ yarn start:dev
----
IMPORTANT: The webapp will automatically open (http://localhost:3006) in your browser and watch for file changes.
When running locally, the available services list is mocked, and service urls set via env vars.
The webapp will also automatically load the walkthroughs from `../tutorial-web-app-walkthroughs/walkthroughs`.
=== Cluster configuration
If you are running tutorial-web-app against your cluster, then you will need to configure your cluster to allow callback to your localhost:
[source,shell]

# first workable clojure script project.
## step1
create a new project with <project-name>
```
lein new figwheel <project-name> -- --reagent
cd <project-name>
npm install
```
## step2
(optional), do it only if you cannot properly work. make a few changes in project.clj, remember to replace all localhost to your IP
```
; under :figwheel add
:figwheel {:on-jsload "figwheel1.core/on-js-reload"
           :websocket-host "192.168.1.42"
           :websocket-url "ws://192.168.1.42:3449/figwheel-ws"
;...
					 :open-urls ["http://192.168.1.42:3449/index.html"]}
; unremark server-ip and put your fixed ip
:figwheel {;; :http-server-root "public" ;; default and assumes "resources"
             ;; :server-port 3449 ;; default
             :server-ip "192.168.1.42"	 
```
at last, you might need to change if it changed, in the file: resources\public\js\compiled\out\figwheel\connect.js
```
// change ws://localhost:3449/figwheel-ws to
ws://192.168.1.42:3449/figwheel-ws
```
## step3
then run it 
```
lein figwheel
```






# figwheel1

FIXME: Write a one-line description of your library/project.

## Overview

FIXME: Write a paragraph about the library/project and highlight its goals.

## Setup

To get an interactive development environment run:

    npm install
    lein figwheel

and open your browser at [localhost:3449](http://localhost:3449/).
This will auto compile and send all changes to the browser without the
need to reload. After the compilation process is complete, you will
get a Browser Connected REPL. An easy way to try it is:

    (js/alert "Am I connected?")

and you should see an alert in the browser window.

To clean all compiled files:

    lein clean

To create a production build run:

    lein do clean, cljsbuild once min

And open your browser in `resources/public/index.html`. You will not
get live reloading, nor a REPL. 

## License

Copyright © 2014 FIXME

Distributed under the Eclipse Public License either version 1.0 or (at your option) any later version.

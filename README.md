# Server
Server for Question App and Movie Quiz App. 

## Technical Guide
needed three repositories to set the whole game: `quiz`,`question`,and `server`repositories.
### Preparing Servers
As the Apps are develop under development server `developer.cege.ucl.ac.uk`,
### Get two apps from GitHub

### Open Apps in web version
First go to server folder and trigger Node.js
```
cd code/server
node httpServer.js
```
### Open Apps on mobile device

## Summary
### About the Apps

#### functions

#### Interface
* It is relatively comfusing to adjust interface display as MDL has a lot of `css` classes. 
* And to fit the same content on different size of device are not easy. As so, the user guide in `HELP` button needs more work digging into proper `css` style.
### About server and database
* Without Database quesry support, the comparing or filtering iis more complex without constraint check
* As Node.js Express Framework use `app.use(express.static(__dirname));` allow us get static file 
on ubuntu server. The AJAX action are easier achieved 

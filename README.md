# Server
Server for Question App and Movie Quiz App. 

## Technical Guide
needed three repositories to set the whole game: `quiz`,`question`,and `server`repositories.
### Preparing Servers
As the Apps are develop under development server `developer.cege.ucl.ac.uk`, 
### Get two apps from GitHub

To make the apps work, there will be two servers running at the same time: HTTP server access to Ubuntu machine; PhoneGap server access to app. 
### Open Apps in web version
1. Go to `server` folder in commend line terminal and trigger Node.js
```
cd code/server
node httpServer.js
```
2. Move back a layer and shift to app repository (take `quiz` for example)
```
cd ..
cd quiz/
node httpServer.js
```
### Open Apps on mobile device

## Summary
Most test are easier carried out on web version on Chrome since the browser have nice debugging ability.
The IE web version of both apps perform the best among Chrome, IE and mobile PhoneGap App. As AJAX the function serving file on server works only on IE. Thus web version can monitor the detail of all errors, easier to handle errors.
### About the Apps
* Quiz app the loop of checking correct answer works. 
  * Successed in loading question layer but failed at creating Approxiate seacrch.
* Question app:
  * successfully done the coursework requirement. with help.html AJAX popup. 
  * And create simple check when submit the form. Check if the correct answer equals to one of the option choices. 
#### Interface
* It is relatively comfusing to adjust interface display as MDL has a lot of `css` classes. 
* And to fit the same content on different size of device are not easy. As so, the user guide in `HELP` button needs more work digging into proper `css` style.

### About server and database
* Without Database quesry support, the comparing or filtering iis more complex without constraint check.
* As Node.js Express Framework use `app.use(express.static(__dirname));` allow us get static file 
on ubuntu server. The AJAX action are easier achieved.



# Server
Server for Question App and Movie Quiz App. 

## Technical Guide
Need three repositories to set the whole game: `quiz`,`question`,and `server`repositories. And a Android mobile phone.

### Preparing your phone
To download the app, goes to android phone and allow installation of apps from unknown sources. Goes to **Setting**->**Additional settings**->**Safety and privacy**, under **Device adminstration** control, then turn on the **Unknown source**.

One can use QR code reader through these QR code or go to the webpage to find them.

[Question App](https://build.phonegap.com/apps/3143997/share)

![alt text](https://chart.googleapis.com/chart?chs=150x150&cht=qr&chl=https://build.phonegap.com/apps/3143997/install/i5m_F29VDdeUssRkgrvX&chld=L|1&choe=UTF-8)

[Quiz App](https://build.phonegap.com/apps/3153340/share)

![alt text](https://chart.googleapis.com/chart?chs=150x150&cht=qr&chl=https://build.phonegap.com/apps/3153340/install/xry4UdXysrW5tbDNdGGS&chld=L|1&choe=UTF-8)

### Preparing Servers
As the Apps are develop under development server `developer.cege.ucl.ac.uk`, both laptop and mobile device must connect to UCL network (vpn.ucl.ac.uk) via VPN apps (e.g. Cisco AnyConnect)

### Get two apps from GitHub
To make the apps work, there will be two servers running at the same time: HTTP server access to Ubuntu machine; PhoneGap server access to app. Make sure to connect to UCL network before using your Ubuntu server (here we use BitWise to login to Ubuntu, the SSH port i use on  `developer.cege.ucl.ac.uk`host is 30069).

### Open Apps in web version
1. Go to `server` folder in commend line terminal and trigger Node.js
```
cd code/server
node httpServer.js
```
2. Move back a layer and shift to app repository to 'ucesyku' folder where the app is stored. Trigger PhoneGap server by command: `phonegap serve`(take `quiz` for example)
```
cd ..
cd quiz/ucesyku
phonegap serve
```
### Open Apps on mobile device
Since the App become individual and itself connects to PhoneGap server, user only need to connect HTTP server from terminal. Remember that mobile device also need to open VPN to link to database!
```
cd code/server
node httpServer.js
```
### Database side
The port detail of database connection is stored in Ubuntu server (`/home/studentuser/certs`). It contain the detail of PostgreSQL database. The HTTP server will then link to database and provide REST service that retrieve question data (GET) and upload answer and question form(POST). 

## Summary
Most test are easier carried out on web version on Chrome since the browser have nice debugging ability.
The IE web version of both apps perform the best among Chrome, IE and mobile PhoneGap App. As AJAX the function serving file on server works only on IE. Thus web version can monitor the detail of all errors, easier to handle errors.
### Javascript practice
* Many variables needed to be difined beforehand. And it might cause conflict if one variable already exist in resource libraries. Solution is to avoid global variables.
* As it doesn't have strong type when define variables, use '===' and '!==' instead of '==' or '=' to check type matches.

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
* Without Database quesry support, the comparing or filtering is more complex without constraint check. 
* As Node.js Express Framework use `app.use(express.static(__dirname));` allow us get static file 
on ubuntu server. The AJAX action are easier achieved.



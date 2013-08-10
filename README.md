mediacenterjs-spotify-app
=========================

An app for mediacenterjs enabeling you to play spotify tracks.

version 0.0.1- Basic Spotify playback is working now. You can add your credentials in the settings menu and tracks will play directly through the speakers.
  Playback controls and song information will be implemented later.

Unzip contents of this Gitrepo in the root of MediacenterJS.

Then run the following commands in the root dir of mediacenterjs in terminal/command prompt :

    npm install node-gyp
  
    npm install spotify
  
    npm install spotify-web
  
    npm install lame
  
    npm install speaker
  
These modules are dependent of node-Gyp to install on windows.


Setup issues
-----------------

**Windows and node-gyp**

When you download this application through git (Either through zip or a GIT clone) It's possible you will get an error when trying to start the application.
This is due to the fact that some modules have dependencies that need to be installed. So you need to run the install again. 

    npm install lame 
	or/and
	npm install sqlite3
	
If you run Windows it's likely this install will fail. Especially on a x64 machine because to install the dependencies, NPM uses a module called node-gyp.
Which, in it's turn has dependencies as well. You need to install the following:

Windows 32 bits needs Microsoft Visual Studio C++ 2010 Express. Download here: (http://go.microsoft.com/?linkid=9709949)

Windows (7/8) 64 bits needs Microsoft Windows SDK 7.1 which includes visual studio. Download here: (http://www.microsoft.com/en-us/download/details.aspx?id=8279)
	
If you continue to have trouble installing the modules, Please read the documentation: (https://github.com/TooTallNate/node-gyp)

**I Already have visual studio installed but it's a different version than 2010**

An example of installing lame with visual studio 2012 on Windows:

	npm install lame --msvs_version=2012
	
	
**Version mismatch**

If you get the following message:

	Error: Module version mismatch. Expected 11, got 1.
	
You are running a different version of nodeJs then a certain module expects. You simply need to reinstall the module giving the error.
for example:

	Error: Module version mismatch. Expected 11, got 1.
	    at Module.load (module.js:356:32)
	    at Function.Module._load (module.js:312:12)
	    at Module.require (module.js:364:17)
	    at require (module.js:380:17)
	    at bindings (C:\Users\Jan\Documents\GitHub\mediacenterjs\node_modules\lame\node_modules\bindings\bindings.js:76:44)
	    at Object.<anonymous> (C:\Users\Jan\Documents\GitHub\mediacenterjs\node_modules\lame\lib\bindings.js:1:99)
	    at Module._compile (module.js:456:26)
	    at Object.Module._extensions..js (module.js:474:10)
	    at Module.load (module.js:356:32)
	    at Function.Module._load (module.js:312:12

Indicates that the module Lame is generating the error. so simply type the following to reinstall the module:

	npm install lame
	


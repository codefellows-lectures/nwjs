![CF](https://i.imgur.com/7v5ASc8.png)  Welcome to this NW.js tutorial! :smiley:
=========
Today we will be shipping out an example application developed on **Mac** :apple: OSX to a **Win64** OS.  :computer:  

_Please note: this tutorial is based on an instructional lecture originally presented by Rick Patci.   
Feel free to use this guide to walk through these steps at your leisure._

## Your _node_ environment:
- Please ensure you are using a version of node compatible with the latest NW.js build (at the time of  
this initial documentation, node-v6.1.0).  
- If you have nvm, nodenv, etc. you may also add that particular node version.

## Converting this app:

1. Fork and clone **this** repo 
2. `cd nwjs-tutorial`
3. `npm i`
4. Open in editor.
5. ####The following steps will enable you to develop and test this app before bundling it up for desktop use.
  1. Navigate to `package.json`
  2. Append **`"start": "nw"`** to the scripts option.  
![package.json](https://cloud.githubusercontent.com/assets/12869788/15266877/e828f8ac-1966-11e6-9e03-b99739d24b26.png)  

  3. Recommended: append some explicit `window` options after the scripts option.
    ```javascript
    "window": {
      "title": "Sample NW.js App",
      "toolbar": false,
      "fullscreen": false,
      "width": 700,
      "height": 400,
      "resizable": false
    },
    ```  

## Downloading NW.js Binaries:  
1. **In your browser, navigate to nwjs.io**
2. **We want to specifically build for Windows 64 in this example, which can be found by clicking on `DOWNLOADS`:**
  ![nwjs home](https://cloud.githubusercontent.com/assets/12869788/15453014/d65fc77e-1fb8-11e6-900f-5a17751f2be5.png)

3. **On the resulting page, select the `NORMAL` Windows 64-bit option to begin download:**
  ![nwjs win64](https://cloud.githubusercontent.com/assets/12869788/15453036/7d7cb0a8-1fb9-11e6-983c-3b90fcac504d.png)
4. Next, unzip the contents. The destination of the zip extracts is not crucial in this step.
5. Create a new directory (ex: `mkdir sample-nw-v0.1.0`) that will ultimately be the finished product folder we send off to our user. The location of this directory is not crucial, just somewhere you can remember :wink:
6. Copy all of the extracted contents of the nwjs zip binaries into this new user directory.
7. Now back in our tutorial directory, we need to bundle up our app's files (index.html, styles directory, and the package.json) into a package.nw file. `zip -r package.nw index.html styles package.json` within the directory containing these files.
8. `mv package.nw ../your-path/to/the/user/dir`. The user's directory should now contain our nw.js binaries and the resulting `package.nw` archive.
9. Rename the nw.exe file to an app name of your choosing! ex: `our-cool-example-app.exe`
10. We are now ready to bundle this up officially! You may use the `zip -r` command for recursive directory zip, or, to encrypt with apassword you can pass an extra flag `zip -er`. Once these are bundled up, we are ready to send away! The end-user unzips, and runs the executable :smile:




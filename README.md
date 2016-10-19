# Installing a cordova environment for Adapt building

There are lots and lots of dependancies. This is a technically challenging guide and you will need LOTS of space on your machine.

## Step 1: Install main libraries

1. Install [cordova](https://cordova.apache.org/docs/en/latest/guide/cli/index.html). 

2. Install [cordova-icon](https://www.npmjs.com/package/cordova-icon) and it's dependancies (not easy on OS X)

3. Install [cordova-splash](https://www.npmjs.com/package/cordova-splash) and the same dependancies as cordova-icon

4. Install IOS development environement on OS X. This is easy, just install XCode. 

5. Install [Android SDK](https://developer.android.com/studio/index.html).

6. Once installed run the SDK and install android-23 and android-24 build tools.

7. Ensure ANDROID_HOME is in your path (google search how to do this for your OS).

## Step 2: Create a app

1. Follow [guide](https://cordova.apache.org/docs/en/latest/guide/cli/index.html) to create a new project in cordova.
  * Add the relevant build platforms (cordova platform add ios --save & cordova platform add android --save)

2. Put adapt content in www folder

3. Create an icon.png (2048x2028) in the root folder of the project

4. Download spash.png to the root folder of the project

5. Edit config.xml to name the project and give the description etc (there is a sample in this project)

6. Install the following plugins:
  * cordova plugin add cordova-plugin-inappbrowser
  * cordova-plugin-statusbar 1.0.1
  * cordova-plugin-whitelist 1.0.0 "Whitelist"
  * nl.x-services.plugins.backgroundaudio
  
7. Run cordova-icon & cordova-splash
  
8. Build your project and hope. 

## Step 3: Signing and deploying 

TODO

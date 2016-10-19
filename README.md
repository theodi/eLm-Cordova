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

## Step 3: Signing and deploying (IOS)

You need to be part of the Open Data Institutes team first.

You then need to connect your XCode to this team. This can be done by opening the resultant xCode project that cordova builds in xCode. Once open scroll down to the signing section and add your team account.

From xCode you will probably need to fix the asset catalog of icons (as cordova-icon doesn't appear to generate the correct output for xCode). 

To do this upload your image to [makeappicon](https://makeappicon.com/) and download the resultant catalogue. 

In xCode scroll down further in the general page of the project to the app icons section. Click the right arrow to open the appicon editor. Remove the AppIcon set that is there and then from the add sign select import. Select the IOS folder from inside the zip file that makeappicon provided you. 

To build for distribution, ensure that "generic ios device" is selected as the build target at the top in xcode. 

This will then allow you to build and archive the app ready for submission to iTunes connect.

At this point iTunes connect will review and through back a whole load more errors for you to deal with... good luck! 

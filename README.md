# varnalab-app


## Prepare Environment

### System packages
Install system packages:
```
sudo apt-get install openjdk-8-jdk gradle
```
> Gradle is needed to build cordova project.
> 
> **Please note that this setup won't work with openjdk-9-jdk !!!**

### Android Studio
Download [Android Studio](https://developer.android.com/studio/index.html), unpack it to your favored destination and execute:
```
./path/to/android-studio/bin/studio.sh
```
then follow the install wizard, which will install the android-sdk-linux.

Install API versions required for **cordova** by SDK Manager from `Tools -> Android -> SDK Manager` or `Configure -> SDK Manager`.

### Bash
Update your `.bashrc` file:
```
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export ANDROID_HOME=$HOME/PathToAndroid/Sdk
```

### Node Version Manager
Install nvm (optional but preferable):
```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
# re-log into terminal
nvm install node
```

### Cordova
Install cordova:
```
sudo npm i -g cordova
```
> Use latest Node 8.x for better results

## Deployment
```
git clone --recursive git@github.com:VarnaLab/varnalab-app.git
cd varnalab-app
cordova plugin add cordova-plugin-crosswalk-webview
cordova platform add android
cordova requirements
```
*Please make sure `cordova requirements` command pass without error*. Here's an example success output:
```
Requirements check results for android:
Java JDK: installed 1.8.0
Android SDK: installed true
Android target: installed android-26,android-25,android-19
Gradle: installed /usr/share/gradle/bin/gradle
```

## Running on a device
*Please make sure your phone is connected via USB and Debugging mode is enabled. You will get a notification to accept the computer.*
```
cordova run android
```

## Building .apk

### Creating Signing Key
Execute the command then answer the questions. **You require to do this once**:
```
keytool -genkey -v -keystore varnalab-release-key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias varnalab-alias
```

### Building .apk
Execute command and upload to Google Play Store:
```
cordova build android --release -- --keystore=varnalab-release-key.jks --storePassword='store password here' --alias=arnalab-alias --password='alias password here'
```

## Updating www folder
To update web app you can pull directly:
```
cd www
git pull origin master
cd ..
```

## Resources
- [cordova](https://cordova.apache.org)
- [cordova-plugin-crosswalk-webview](https://www.npmjs.com/package/cordova-plugin-crosswalk-webview)
- [about the crosswalk situation](https://stackoverflow.com/a/18786905/1260020)
- [working with git submodules](https://github.com/blog/2104-working-with-submodules)
- [varnalab.github.io](https://github.com/VarnaLab/varnalab.github.io)

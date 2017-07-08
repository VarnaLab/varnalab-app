
# varnalab-app


## Install Android Environment

1. `sudo apt-get install openjdk-8-jdk`
  + it doesn't work with openjdk-9-jdk !!!

2. `sudo apt-get install gradle`
  + android's build system

3. install [android-studio](https://developer.android.com/studio/index.html)

4. `./path/to/android-studio/bin/studio.sh`
  - follow the install wizard, it will install the android-sdk-linux

5. Tools -> Android -> SDK Manager
  - install API version

6. npm i -g cordova
  - use latest Node 8.x for better results


## Install Project

1. `cordova plugin add cordova-plugin-crosswalk-webview`

2. `cordova platform add android`

3. `cordova requirements`
  + make sure you have all requirements set

4. `cd www`
  + `git pull origin master`
  + `cd ..`

5. make sure you have your phone connected via USB

6. `cordova run android`


## Resources

- [cordova](https://cordova.apache.org)
- [cordova-plugin-crosswalk-webview](https://www.npmjs.com/package/cordova-plugin-crosswalk-webview)
- [about the crosswalk situation](https://stackoverflow.com/a/18786905/1260020)
- [working with git submodules](https://github.com/blog/2104-working-with-submodules)
- [varnalab.github.io](https://github.com/VarnaLab/varnalab.github.io)

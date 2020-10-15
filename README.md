# Install Default JRE/JDK
```bash
sudo apt install default-jre
```
```bash
sudo apt install default-jdk
 ```

# Install Android SDK CLI (Work in Progress)

## Install Java 8

```bash
sudo apt install openjdk-8-jdk-headless
```

## Android SDK

```bash
wget https://dl.google.com/android/repository/commandlinetools-linux-6200805_latest.zip
mkdir -p Android/Sdk
unzip commandlinetools-linux-6200805_latest.zip -d Android/Sdk

export ANDROID_HOME=$HOME/Android/Sdk
# Make sure emulator path comes before tools. Had trouble on Ubuntu with emulator from /tools being loaded
# instead of the one from /emulator
export PATH="$ANDROID_HOME/emulator:$ANDROID_HOME/tools:$ANDROID_HOME/tools/bin:$ANDROID_HOME/platform-tools:$PATH"

sdkmanager --sdk_root=${ANDROID_HOME} "tools"

sdkmanager --update
sdkmanager --list
sdkmanager "build-tools;28.0.3" "platform-tools" "platforms;android-28" "tools"
sdkmanager --licenses

sudo apt install gradle


````

Note: you can get an updated Android SDK link from https://developer.android.com/studio/#downloads

Used a combinaton of these gists:
https://gist.github.com/fedme/fd42caec2e5a7e93e12943376373b7d0
https://gist.github.com/jjvillavicencio/18feb09f0e93e017a861678bc638dcb0

Background on the update to command line tools from android sdk
https://stackoverflow.com/a/61176718

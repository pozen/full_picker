# Full picker
<a href="https://pub.dev/packages/full_picker"><img src="https://img.shields.io/pub/v/full_picker.svg" alt="Pub"></a></br>
A flutter package that helps you in selecting files


## Features
* Multi File picker
* Video Compressor
* Image Cropper
* Custom Camera
* Custom Name For Files


## Usage
Quick simple usage example:

```dart
FullPicker(
  context: context,
  firstPartFileName: "test",
  file: true,
  image: true,
  video: true,
  videoCamera: true,
  imageCamera: true,
  videoCompressor: false,
  imageCropper: false,
  multiFile: true,
  onError: (int value) {
    print(" ----  onError ----=$value");
  },
  onSelected: (value) {
    print(" ----  onSelected ----");
  },
);
```

and use ```minSdkVersion 21``` in your Module-level build.gradle file

### Video Compressor
If you need to compress the video, add the following

#### iOS

Add the following to your _Info.plist_ file, located in `<project root>/ios/Runner/Info.plist`:

```
<key>NSPhotoLibraryUsageDescription</key>
<string>${PRODUCT_NAME} library Usage</string>
```

#### Android

Add the following permissions in AndroidManifest.xml:

**API < 29**

```xml
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"
android:maxSdkVersion="28"/>
```

**API >= 29**

```xml
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
```

Include this in your Project-level build.gradle file:
```groovy
allprojects {
    repositories {
        .
        .
        .
        maven { url 'https://jitpack.io' }
    }
}
```

Include this in your Module-level build.gradle file:

```groovy
implementation 'com.github.AbedElazizShe:LightCompressor:1.0.0
```

### Image Cropper
If you need to crop the image, add the following

#### Android

- Add UCropActivity into your AndroidManifest.xml

````xml
<activity
    android:name="com.yalantis.ucrop.UCropActivity"
    android:screenOrientation="portrait"
    android:theme="@style/Theme.AppCompat.Light.NoActionBar"/>
````

#### iOS
- No configuration required


## Example App
<img src="https://raw.githubusercontent.com/mbfakourii/full_picker/master/example/screenshots/example.gif" width="300" height="550" />

## Getting Started

For help getting started with Flutter, view our online
[documentation](https://flutter.io/).

For help on editing plugin code, view the [documentation](https://flutter.io/platform-plugins/#edit-code).




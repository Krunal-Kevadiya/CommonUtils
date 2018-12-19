[![API](https://img.shields.io/badge/API-16%2B-red.svg?style=flat)](https://android-arsenal.com/api?level=16)
[![Build Status](https://travis-ci.org/wupdigital/android-maven-publish.svg?branch=master)](https://github.com/Krunal-Kevadiya/CommonUtils)
[ ![Download](https://api.bintray.com/packages/kevadiyakrunalk/MyFramework/commonutils/images/download.svg) ](https://bintray.com/kevadiyakrunalk/MyFramework/commonutils/_latestVersion) 
[![License](https://img.shields.io/badge/License-Apache%202.0-orange.svg)](https://opensource.org/licenses/Apache-2.0)

# CommonUtils

## Log-cat
* for use display your value in console with class name, which line number to call and your data set.
* Code :-
```java
   Logs.getInstance(this).verbose(TAG, Message);
   Logs.getInstance(this).debug(TAG, Message);
   Logs.getInstance(this).info(TAG, Message);
   Logs.getInstance(this).warn(TAG, Message);
   Logs.getInstance(this).error(TAG, Message);
```

## Image Compressor
* you can compress image with based on maxWidth, maxHeight, format and quality.
* Code :-
```java
   new Compressor.Builder(this, this.getFilesDir().getPath()) //path is destination file to which location save
       .setMaxWidth(612.0f) //[optional] set the resultan image/photo maximum width
       .setMaxHeight(816.0f) //[optional] set the resultan image/photo maximum height
       .setQuality(80) //[optional] set the result image quality.
       .build()
       // set dialog button, use Either compressToFileAsObservable or compressToBitmapAsObservable
       .compressToFileAsObservable(file) //file is your want to compress image/photo path
       .compressToBitmapAsObservable(file) //file is your want to compress image/photo path
       
       .subscribe(new Action1<File/*set argument based on your are use above two function [File/Bitmap] */>() {
           @Override
           public void call(File file) {
               logs.error("Compressor", "File -> " + (file.length()/1024) + " KB");
           }
       });
```

## Drawable Color Change
* change drawable color for example your image is white color then you can change same image into red color.
* Code :-
```java
   imageView.setImageDrawable(
     DrawableColorChange.getInstance(this).changeColorById(R.drawable.ic_file, R.color.colorAccent));
   imageView.setImageDrawable(
     DrawableColorChange.getInstance(this).changeColorByColor(ContextCompat.getDrawable(this, R.drawable.ic_file),
     Color.Red));  
```

## EventBus
* used for data passing from one class to other class.

-> Gradle
```groovy
//add dependencies for app level build.gradle
repositories {
    jcenter()
}
dependencies {
  compile 'com.kevadiyakrunalk:commonutils:1.1@aar'
}
```
-> Maven
```xml
<dependency>
  <groupId>com.kevadiyakrunalk</groupId>
  <artifactId>commonutils</artifactId>
  <version>1.1</version>
  <type>pom</type>
</dependency>
```
